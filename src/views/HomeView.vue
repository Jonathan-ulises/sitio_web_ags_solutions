<template>
  <div>
    <hello-world />
    <carousel />
    <CardRectora />
    <Noticias />
    <br>
    <br>
    <br>
    <br>
    <link rel="stylesheet" href="../assets/LogoUTL_Blanco.png">

    <footer class="footer" style="background-color: #ffffff; position: relative;">
      <div class="container">
        <!-- Imagen que abarca todo el footer -->
        <v-img
          src="@/assets/fondos/cintillo.jpeg"
          class="footer-image"
          cover
        ></v-img>
      </div>
    </footer>
  
    <footer class="footer" style="background-color: #003082; text-align: center;">
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
import MenuSuperior from '../components/MenuSuperior.vue'
import Carousel from '../components/Carousel.vue'
import CardRectora from '../components/CardRectora.vue'
import HelloWorld from '../components/HelloWorld'
import Noticias from '../components/Noticias.vue'

window.document.title = 'Universidad Tecnológica de León';

export default {
  name: 'Home',

  components: {
    HelloWorld,
    Carousel,
    CardRectora,
    MenuSuperior,
    Noticias
 
  },
}
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
height: auto;
position: absolute;
width: 100%;
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
