<template>
    <section style="padding-top: 3em; bottom: 0;">
        <footer class="footer is-primary fondo">
            <div>
                <span class="is-pulled-right has-text-white">
                    <img src="@/assets/logo.jpeg" alt="logo" width="125" height="125">   
                </span>
                <p class="titulo content has-text-centered title is-3 has-text-white">
                    <strong>Sitio desarrollado por CulinaryCenter</strong>
                </p>  
            </div>
            <div style="margin-top: 1rem;">
                <p class="titulo content has-text-centered title is-3 has-text-white">
                    <strong>Contactanos</strong>
                    <a href="https://mail.google.com/" target="_blank" rel="noopener noreferrer">
                        <button class="button is-white is-rounded" @click="contactEmail">
                        <b-icon icon="email"></b-icon>
                    </button>
                    </a>
                    <a href="https://www.facebook.com/" target="_blank" rel="noopener noreferrer">
                        <button class="button is-white is-rounded" @click="contactFacebook">
                        <b-icon icon="facebook"></b-icon>
                    </button>
                    </a>
                    <a href="https://twitter.com/" target="_blank" rel="noopener noreferrer">
                        <button class="button is-white is-rounded">
                            <b-icon icon="twitter"></b-icon>
                        </button>
                    </a>
                </p>
            </div>

        </footer>
    </section>
</template>
<script>
import HttpService from '../Servicios/HttpService'
export default {
    name: "Pie",

    data: () =>({
        datosLocal: {}
    }),

    mounted(){
        this.obtenerDatos()
    },

    methods: {
        obtenerDatos(){
            HttpService.obtener("obtener_datos_local.php")
            .then(resultado => {
                this.datosLocal = resultado
            })
        }
    }
}
</script>
