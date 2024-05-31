<template>
    <div class="container">
      <h2>Lista de Videojuegos</h2>
      <table>
        <thead>
          <tr>
            <th>Título</th>
            <th>Plataforma</th>
            <th>Estado</th>
            <th>Puntaje</th>
            <th>Acciones</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="videojuego in videojuegos" :key="videojuego.titulo">
            <td data-label="Título">{{ videojuego.titulo }}</td>
            <td data-label="Plataforma">{{ videojuego.plataforma }}</td>
            <td data-label="Estado">{{ videojuego.estado }}</td>
            <td data-label="Puntaje">{{ videojuego.puntaje }}</td>
            <td data-label="Acciones"><button @click="$emit('ver-detalles', videojuego)">Detalles</button></td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    props: ['videojuegos']
  };
  </script>
  