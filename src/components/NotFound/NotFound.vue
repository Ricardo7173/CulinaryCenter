<template>
    <div class="not-found">
        <h1>404 - Página no encontrada</h1>
        <p>Lo sentimos, la página que buscas no se encontró.</p>
        <div class="background-image"></div>
        <router-link to="/" class="home-button">Volver al inicio</router-link>
    </div>
</template>
  
<script>
export default {
    name: 'NotFound'
}
</script>
  
<style scoped>
.not-found {
    position: relative;
    text-align: center;
    color: white;
    /* Color del texto */
}

.background-image {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url('../../assets/eror-404.jpg');
    /* Ruta de tu imagen */
    background-size: cover;
    /* Cubre toda la pantalla */
    background-position: center;
    /* Centra la imagen */
    z-index: -1; /* Coloca la imagen detrás del contenido */
    filter: brightness(0.5);
    /* Opcional: ajusta el brillo de la imagen */
}

.home-button {
    margin-top: 20px;
    display: inline-block;
    padding: 10px 20px;
    background-color: #007bff;
    /* Color del botón */
    color: white;
    text-decoration: none;
    border-radius: 5px;
    transition: background-color 0.3s ease;
}

.home-button:hover {
    background-color: #0056b3;
    /* Color del botón al pasar el cursor */
}</style>
  