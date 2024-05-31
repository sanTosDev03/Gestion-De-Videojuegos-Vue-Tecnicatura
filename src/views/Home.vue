<template>
  <div>
    <RegistroVideojuego @registrar-videojuego="agregarVideojuego"/>
    <ListaVideojuegos :videojuegos="videojuegos" @ver-detalles="mostrarDetalles"/>
    <DetallesVideojuego :videojuego="videojuegoSeleccionado"/>
  </div>
</template>

<script>
import RegistroVideojuego from '@/components/RegistroVideojuego.vue';
import ListaVideojuegos from '@/components/ListaVideojuegos.vue';
import DetallesVideojuego from '@/components/DetallesVideojuego.vue';

export default {
  name: 'HomeView',
  components: {
    RegistroVideojuego,
    ListaVideojuegos,
    DetallesVideojuego
  },
  data() {
    return {
      videojuegos: [],
      videojuegoSeleccionado: null
    };
  },
  methods: {
    agregarVideojuego(videojuego) {
      this.videojuegos.push(videojuego);
    },
    mostrarDetalles(videojuego) {
      this.videojuegoSeleccionado = videojuego;
    }
  }
};
</script>

  