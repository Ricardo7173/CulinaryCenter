<template>
  <div id="app">
    <configuracion-inicial v-if="configurar" />
    <login @logeado="onLog" v-if="!logeado && !configurar"></login>
    <cambiar-password v-if="cambiarPassword"></cambiar-password>
    <div v-if="logeado && !cambiarPassword">
      <div v-if="mostrarEncabezadoPie"> <!-- Aquí se inicia la condición para mostrar el encabezado-->
        <encabezado @cerrar="onClose" />
      </div> <!-- Aquí se cierra la condición para mostrar el encabezado-->
      <div class="container">
        <router-view />
      </div>
      <div v-if="mostrarEncabezadoPie"> <!-- Aquí se inicia la condición para mostrar el pie -->
        <pie v-if="logeado || cambiarPassword" />
        <!-- Aquí se cierra la condición para mostrar el pie -->
      </div>
    </div>
  </div>
</template>

<script>
import useRouter from 'vue-router'; // Importa el módulo useRouter de Vue Router
import Login from './components/Usuarios/Login.vue'
import CambiarPassword from './components/Usuarios/CambiarPassword.vue'
import ConfiguracionInicial from './components/Configuracion/ConfiguracionInicial.vue'
import Encabezado from './components/Encabezado.vue'
import Pie from './components/Pie.vue'
import HttpService from './Servicios/HttpService'

export default {
  components: { Encabezado, Pie, Login, CambiarPassword, ConfiguracionInicial },
  name: 'App',

  data: () => ({
    logeado: false,
    datos: "",
    cambiarPassword: false,
    configurar: false,
    mostrarEncabezadoPie: true // Inicialmente establecido en true
  }),

  mounted() {
    this.verificarInformacion()
    let logeado = this.verificarSesion()
    if (logeado) {
      this.logeado = true
    }
  },

  methods: {
    verificarInformacion() {
      HttpService.obtener("verificar_tablas.php")
        .then(resultado => {
          if (resultado.resultado > 0) {
            this.configurar = false
            return
          }

          this.configurar = true
          return
        })
    },

    verificarSesion() {
      let logeado = localStorage.getItem('logeado')
      if (logeado) {
        return logeado
      }
      return false
    },

    onLog(logeado) {
      if (logeado.resultado === "cambia") {
        this.cambiarPassword = true
        this.logeado = true
        localStorage.setItem('nombreUsuario', logeado.datos.nombreUsuario)
        localStorage.setItem('idUsuario', logeado.datos.idUsuario)
        return
      }

      if (logeado.resultado) {
        this.logeado = true
        localStorage.setItem('logeado', true)
        localStorage.setItem('nombreUsuario', logeado.datos.nombreUsuario)
        localStorage.setItem('idUsuario', logeado.datos.idUsuario)
      }

    },

    onClose(logeado) {
      this.logeado = logeado
    }
  },

  created() {
    const router = this.$router; // Obtiene la instancia del enrutador

    // Observa los cambios de ruta y actualiza mostrarEncabezadoPie en consecuencia
    router.afterEach((to, from) => {
      if (to.meta && to.meta.noMostrarEncabezadoPie) {
        this.mostrarEncabezadoPie = false;
      } else {
        this.mostrarEncabezadoPie = true;
      }
    });
}

}
</script>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  /* Establece la altura mínima del contenedor al 100% de la altura del viewport */
}

.container {
  flex: 1;
  /* El contenido se expandirá para llenar el espacio restante */
}

.pie {
  background-color: #333;
  /* Color de fondo del footer */
  color: white;
  /* Color del texto del footer */
  padding: 20px;
  text-align: center;
}</style>
