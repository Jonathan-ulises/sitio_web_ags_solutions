<template>
  <div>
    <hello-world />
    <carousel />
    <CardRectora />
   

  </div>
</template>

<script>
import MenuSuperior from '../components/MenuSuperior.vue'
import Carousel from '../components/Carousel.vue'
import CardRectora from '../components/CardRectora.vue'
import HelloWorld from '../components/HelloWorld'

export default {
  name: 'Home',

  components: {
    HelloWorld,
    Carousel,
    CardRectora,
    MenuSuperior
  },
}
</script>

