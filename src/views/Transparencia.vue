<template>
    <div>
      <div>
    <v-img src="../assets/fondos/transparencia.png" style="margin-top: -100px; z-index: 1; box-shadow: 0px 50px 50px rgba(0, 0, 0, 0.5);"
    max-height
    with
    cover
    aspect-ratio="16/9">
    <p class="text-h1 text-start font-weight-class text-right"
    style="color:#00B394; font-family: 'Roboto Flex', sans-serif;font-weight: bold; margin-top: 250px; margin-left: 1%;">
   Transparencia
 </p>
    </v-img>
      </div>
      <card>
        <v-row>
          <v-col md="1"></v-col>
          <v-col md="10">
            <br>
            <br>
            <br>
            <p class="text-justify" style="font-family: 'Roboto Flex', sans-serif;  font-size: 19px">
                Porque accesar a la información pública es un ejercicio del derecho humano de las y los ciudadanos, la Universidad Tecnológica de León organiza, conserva y difunde en esta vitrina digital, aquella documentación de competencia pública, en cumplimiento a las obligaciones de transparencia y la información proactiva, establecidas en la Ley de Transparencia y Acceso a la Información para el Estado de Guanajuato
            </p>
          </v-col>
        </v-row>
      </card>
      <card >
        <v-row class="justify-md-content-center">
          <v-col md="12"></v-col>
          
          <v-col md="3" class="text-center justify-content-center elemento" style="margin-left: 300px;">
            <br>
            <br>
            <br>
            <v-img src="../assets/fondos/finanzas.png" :width="180"></v-img>
          </v-col>
        
          <v-col md="3" class="text-center justify-content-center elemento">
            <br>
            <br>
            <br>
            <v-img src="../assets/fondos/controsocial.png" :width="180"></v-img>
          </v-col>
          <v-col md="3" class="text-center justify-content-center elemento">
            <br>
            <br>
            <br>
            <v-img src="../assets/fondos/obligaciones.png" :width="180"></v-img>
          </v-col>
          <v-col md="3" class="text-center justify-content-center font-weight-bold" style="margin-left: 200px; font-family: 'Roboto', sans-serif; margin-top: -40px;">
            <br>
            <br>
            <br>
            <p class="text-h5 font-weight-bold">Finanzas</p>
          </v-col>
          <v-col md="3" class="text-center justify-content-center font-weight-bold" style="font-family: 'Roboto', sans-serif ; margin-top: -40px;">
            <br>
            <br>
            <br>
            <p class="text-h5 font-weight-bold">Controlaría Social</p>
          </v-col>
          <v-col md="3" class="text-center justify-content-center font-weight-bold" style="font-family: 'Roboto', sans-serif; margin-top: -40px;">
            <br>
            <br>
            <br>
            <p class="text-h5 font-weight-bold">Obligaciones de transparencia</p>
          </v-col>
        </v-row>
      </card>
      <br>
    <br>
    <br>
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

  <style>
  
  .elemento:hover{
    transform: scale(1.2);
  }

  .elemento{
    transition: 1s;
    
  }
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