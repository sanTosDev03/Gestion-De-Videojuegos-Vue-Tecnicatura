<template>
    <div class="container">
      <h2>Registrar Videojuego</h2>
      <form @submit.prevent="registrarVideojuego">
        <div>
          <label for="titulo">Título</label>
          <input v-model="videojuego.titulo" type="text" id="titulo" required>
        </div>
        <div>
          <label for="plataforma">Plataforma</label>
          <select v-model="videojuego.plataforma" id="plataforma" required>
            <option>PC</option>
            <option>PS4</option>
            <option>Xbox</option>
            <!-- Añade más plataformas según sea necesario -->
          </select>
        </div>
        <div>
          <label for="estado">Estado</label>
          <select v-model="videojuego.estado" id="estado" required>
            <option>Completado</option>
            <option>En progreso</option>
            <option>Abandonado</option>
            <!-- Añade más estados según sea necesario -->
          </select>
        </div>
        <div>
          <label for="puntaje">Puntaje (opcional)</label>
          <input v-model="videojuego.puntaje" type="number" id="puntaje" min="1" max="10">
        </div>
        <button type="submit">Registrar Videojuego</button>
      </form>
      <div v-if="error" class="error">{{ error }}</div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        videojuego: {
          titulo: '',
          plataforma: '',
          estado: '',
          puntaje: null
        },
        error: null
      };
    },
    methods: {
      registrarVideojuego() {
        if (!this.videojuego.titulo || !this.videojuego.plataforma || !this.videojuego.estado) {
          this.error = 'Todos los campos son requeridos, excepto el puntaje.';
          return;
        }
        if (this.videojuego.puntaje && (this.videojuego.puntaje < 1 || this.videojuego.puntaje > 10)) {
          this.error = 'El puntaje debe estar entre 1 y 10.';
          return;
        }
        this.$emit('registrar-videojuego', { ...this.videojuego });
        this.videojuego.titulo = '';
        this.videojuego.plataforma = '';
        this.videojuego.estado = '';
        this.videojuego.puntaje = null;
        this.error = null;
      }
    }
  };
  </script>
  
  <style scoped>
  .error {
    color: red;
  }
  </style>
  
  
  