<template>
    <div class="carousel-container">
      <v-carousel cycle height="747" hide-delimiters :next-icon="null" :prev-icon="null">
        <v-carousel-item
          v-for="(item, i) in items"
          :key="i"
          :src="item.src"
          reverse-transition="fade-transition"
          transition="fade-transition"
        ></v-carousel-item>
      </v-carousel>
    </div>
  </template>
  
  <script>
  import MenuSuperior from '../components/MenuSuperior.vue';
  
  export default {
    components: {
      MenuSuperior
    },
    data: () => ({
      items: [
        {
          src: require('@/assets/fondos/fondo_estudiante.jpeg')
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
        },
      ],
    }),
  };
  </script>
  
  <style scoped>
  .carousel-container {
    position: relative;
    width: 100%;
    height: 747px; /* Ajusta la altura según tus necesidades */
  }
  
  /* Estilo para posicionar el menú superior de forma absoluta */
  .MenuSuperior {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1; /* Asegura que el menú esté sobre el carrusel */
  }
  </style>
  