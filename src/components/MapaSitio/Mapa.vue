<template>
    <div class="mapa-sitio">
        <p class="title is-1 has-text-weight-bold">
            <b-icon
                icon="sitemap-outline"
                size="is-large"
                type="is-primary">
            </b-icon>
            Mapa del Sitio 
        </p>
      <ul>
        <li><router-link :to="{ name: 'Inicio' }">Inicio</router-link></li>
        <li><router-link :to="{ name: 'Insumos' }">Alimentos</router-link></li>
        <li><router-link :to="{ name: 'RealizarOrden' }">Ordenar</router-link></li>
        <li><router-link :to="{ name: 'Categorias' }">Categorías</router-link></li>
        <li><router-link :to="{ name: 'Usuarios' }">Usuarios</router-link></li>
        <li><router-link :to="{ name: 'EditarUsuario', params: { id: 'id_ejemplo' } }">Editar Usuario</router-link></li>
        <li><router-link :to="{ name: 'ReporteVentas' }">Reporte de Ventas</router-link></li>
        <li><router-link :to="{ name: 'Configurar' }">Configurar</router-link></li>
        <li><router-link :to="{ name: 'Mapa' }">Mapa del Sitio</router-link></li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'MapaSitio'
  }
  </script>
  
  <style scoped>
  .mapa-sitio {
    text-align: left;
  }
  
  ul {
    list-style: none;
    padding: 0;
    display: flex; /* Establece el contenedor como flexbox */
    justify-content: center; /* Centra los elementos horizontalmente */
    flex-wrap: wrap; /* Permite que los elementos se envuelvan en múltiples líneas si no caben en una sola línea */
  }
  
  li {
    margin: 10px; /* Añade espacio entre los elementos */
  }
  </style>
  