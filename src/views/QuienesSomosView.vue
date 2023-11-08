<template>
  <div>
    
    
    <v-img 
      class="image-overlay"
      src="../assets/fondo_quienesomos.svg"
      style="margin-top: -100px; z-index: 1;"
      max-height
      with
      cover
      aspect-ratio="16/9"
    >

    <p class="text-h1 text-start font-weight-class text-right"
       style="color:#00B394; font-family: 'Roboto Flex', sans-serif;font-weight: bold; margin-top: 250px; margin-left: 1%;">
      Historia
    </p>
    </v-img>

    <card>
      <v-row>
        <v-col md="1"></v-col>
        <v-col md="10">
          <br>
          <br>
          <br>
          <p class="text-justify" style="font-family: 'Roboto Flex', sans-serif; font-size: 19px;">
            La Universidad Tecnológica de León inició su funcionamiento el 26 de septiembre de 1995, con la inauguración de cursos efectuada por el C. Vicente Fox Quesada, Gobernador Constitucional del Estado de Guanajuato, ante la presencia de altas personalidades del gobierno federal, estatal, municipal y la comunidad universitaria.
          </p>
          <p class="text-justify" style="font-family: 'Roboto Flex', sans-serif; font-size: 19px;">
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
          <div class="carousel-container" style="margin: 20px; padding: 20px;">
            <v-carousel
                cycle
                height="600"
                width="500"
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
            



            <!--<div v-cloak>
           <div @click="scrollToTop" class="fixed right-0 bottom-0" style="height: 100px;">
          <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-arrow-bar-up" viewBox="0 0 16 16">
  <path fill-rule="evenodd" d="M8 10a.5.5 0 0 0 .5-.5V3.707l2.146 2.147a.5.5 0 0 0 .708-.708l-3-3a.5.5 0 0 0-.708 0l-3 3a.5.5 0 1 0 .708.708L7.5 3.707V9.5a.5.5 0 0 0 .5.5zm-7 2.5a.5.5 0 0 1 .5-.5h13a.5.5 0 0 1 0 1h-13a.5.5 0 0 1-.5-.5z"/>
</svg></div></div>-->
        </div>
        
        </v-col>
      </v-row>
    </card>
    <br>
    <br>
    <br>
    <footer class="footer" style="background-color: #003082; position: relative;">
      <div class="container">
        <!-- Imagen que abarca todo el footer -->
        <v-img
          src="@/assets/fondos/cintillo.jpeg"
          class="footer-image"
          cover
        ></v-img>
      </div>
    </footer>
    <footer class="footer" style="background-color: #003082;">
      <div class="container">
        <div class="icon-container">
          <v-icon class="social-icon mdi mdi-twitter"></v-icon>
          <v-icon class="social-icon mdi mdi-facebook"></v-icon>
          <v-icon class="social-icon mdi mdi-instagram"></v-icon>
          <v-icon class="social-icon mdi mdi-youtube"></v-icon>
        </div>
        <p style="font-family: 'Roboto Flex', sans-serif; color: #ffffff; margin-top: 20px;">
            Blvd. Universidad Tecnológica #225 Col. San Carlos
        </p>
        <p style="font-family: 'Roboto Flex', sans-serif; color: #ffffff;">
            CP. 37670 León, Gto. Mex. l Tel (477) 7 10 00 20
        </p>
        
      </div>
  </footer>
  </div>
  

</template>

<script>

export default {
  data() {
    return {
      items: [
        {
          src: require('@/assets/carouseles/imagen1.png')
        },
        {
          src: require('@/assets/carouseles/imagen2.png')
        },
        {
          src: require('@/assets/carouseles/imagen3.png')
        },
        {
          src: require('@/assets/carouseles/imagen4.png')
        },
        {
          src: require('@/assets/carouseles/imagen5.png')
        },
      ]
    };
  },
  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, left: 0, behavior: 'smooth' });
    },
  },
};





</script>

<style>
/* Estilos CSS para tu componente aquí */
.social-icon {
  font-size: 40px;
  color: #ffffff;
  background-color: #ffffff;
  border-radius: 50%;
  padding: 10px;
  margin: 10px;
  transition: 0.3s;
}
.social-icon:hover {
  transform: scale(1.2);
}


.footer {
background-color: #1f2a34;
padding: 20px 0;
text-align: center;
}
.footer-image {
width: 100%; /* Asegura que la imagen abarque todo el ancho */
height: 120%; /* Asegura que la imagen tenga la misma altura que el footer */
object-fit: cover; /* Mantiene las proporciones y cubre el área asignada */
position: absolute; /* Posiciona la imagen absolutamente dentro del footer */
top: 0;
left: 0;
}




</style>

