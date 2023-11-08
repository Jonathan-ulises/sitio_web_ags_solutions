<template>
  <v-carousel cycle height="747" hide-delimiters :next-icon="null" :prev-icon="null">
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
      reverse-transition="fade-transition"
      transition="fade-transition"
    ></v-carousel-item>
    </v-carousel>

    
      
</template>


<script>
export default{
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

  })
}
</script>