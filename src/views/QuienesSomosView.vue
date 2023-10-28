<template>
  <div>
    <div>
  <v-img src="../assets/fondo_quienesomos.svg" max-height with cover aspect-ratio="16/9">
    <p class="text-h1 text-start font-weight-class" style="color:#00B394; font-family: 'Roboto Flex', sans-serif;font-weight: bold; margin-top: 200px;">Historia</p>
  </v-img>
    </div>
    <card>
      <v-row>
        <v-col md="1"></v-col>
        <v-col md="10">
          <br>
          <br>
          <br>
          <p class="text-justify" style="font-family: 'Roboto Flex', sans-serif;">
            La Universidad Tecnológica de León inició su funcionamiento el 26 de septiembre de 1995, con la inauguración de cursos efectuada por el C. Vicente Fox Quesada, Gobernador Constitucional del Estado de Guanajuato, ante la presencia de altas personalidades del gobierno federal, estatal, municipal y la comunidad universitaria.
          </p>
          <p class="text-justify" style="font-family: 'Roboto Flex', sans-serif;">
            Desde el 25 de septiembre de 1995 y hasta la fecha, formamos ciudadanos y ciudadanas de bien, con pensamiento global y acción local, con innovación, profundos valores humanos y universales y sobre todo, brindando educación tecnológica y de calidad, orientada a la industria 4.0 y la mente-factura.
          </p>
        </v-col>
      </v-row>
    </card>
    <card style="border-radius: 50px;">
      <v-row class="justify-md-content-center">
        <v-col md="12"></v-col>
        <v-col md="12" class="text-center justify-content-center">
          <br>
          <br>
          <br>
          <v-carousel
    cycle
    height="600"
    width="800"
    hide-delimiter-background
    show-arrows="hover"
    style="border-radius: 50px; box-shadow: 10px 5px 5px rgba(0, 0, 0, 0.437);"
    
    
  >
    <v-carousel-item
      v-for="(item, i) in items"
      :key="i"
      :src="item.src"
      height="1080"
      width="2000"
      
    >
    </v-carousel-item>
  </v-carousel>
        </v-col>
      </v-row>
    </card>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          {
            src: require('@/assets/carouseles/quienessomos/imagen1.png')
          },
          {
            src: require('@/assets/carouseles/quienessomos/imagen2.png')
          },
          {
            src: require('@/assets/carouseles/quienessomos/imagen3.png')
          },
          {
            src: require('@/assets/carouseles/quienessomos/imagen4.png')
          },
          {
            src: require('@/assets/carouseles/quienessomos/imagen5.png')
          },
        ]
      }
    },
  }
</script>