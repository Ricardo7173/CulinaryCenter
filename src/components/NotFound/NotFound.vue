<template>
    <div class="error-container">
      <div class="error-content">
        <h1>¡Oops!</h1>
        <p>Parece que te has perdido en el ciberespacio.</p>
        <p>No te preocupes, estamos aquí para ayudarte a volver al camino correcto.</p>
        <div class="background-image"></div>
        <router-link to="/" class="home-button">Volver al inicio</router-link>
      </div>
    </div>
  </template>

<style scoped>
.error-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-size: cover;
  background-position: center;
}

.error-content {
  text-align: center;
  background-color: rgba(255, 255, 255, 0.501); /* Fondo semi-transparente para que el texto sea legible */
  padding: 20px;
  border-radius: 10px;
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

h1 {
  font-size: 3em;
  color: #e74c3c;
}

p {
  margin: 10px 0;
}

button {
  padding: 10px 20px;
  font-size: 1em;
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #2980b9;
}

.home-button:hover {
    background-color: #0056b3;
    /* Color del botón al pasar el cursor */
}
</style>

