<template>
    <div class="container" v-if="videojuego">
      <h2>Detalles del Videojuego</h2>
      <p><strong>Título:</strong> {{ videojuego.titulo }}</p>
      <p><strong>Plataforma:</strong> {{ videojuego.plataforma }}</p>
      <p><strong>Estado:</strong> {{ videojuego.estado }}</p>
      <p><strong>Puntaje:</strong> {{ videojuego.puntaje }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['videojuego']
  };
  </script>
  
  
  