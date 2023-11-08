<template>
  <div>
    <br>

    <v-row class="mb-4 justify-center align-center">
      <v-col cols="12" md="3" class="mx-1 mb-0 pb-0">
        <v-card class="mx-auto pa-0" max-width="400" style="margin-bottom: 0;">
          <v-img
            src="../assets/fondos/noticias.jpeg"
            height="420px"
            cover
            id="entornosTSU"
          >
            <p class="text-h6 text-left text-weight-bold mb-4" id="textoEntornos" style="font-family: 'Roboto Flex', sans-serif; color:white; margin-top: 280px; margin-left: 30px; margin-right: 30px; margin-bottom: 30px;">1er Encuentro de egresados GTO</p>
            <v-row class="d-flex align-center mb-2">
              <v-col cols="auto">
                <p class="text-h6" style="color:white; font-family: 'Roboto Flex', sans-serif; margin-left: 30px; margin-right: 0px; margin-top: -8px;">Leer más</p>

              </v-col>
              <v-col cols="auto">
              
                <v-img src="../assets/fondos/carrerastsu/flecha.png" max-height="40px" max-width="40px"></v-img>
                <br>
              </v-col>
            </v-row>
          </v-img>
        </v-card>
        
        
      </v-col>
      <v-col cols="12" md="3" class="mx-1 mb-0 pb-0">
        <v-card class="mx-auto pa-0" max-width="400" style="margin-bottom: 0;">
          <v-img
            src="../assets/fondos/noticias1.jpeg"
            height="420px"
            cover
            id="entornosTSU"
          >
            <p class="text-h6 text-left text-weight-bold mb-4" id="textoEntornos" style="font-family: 'Roboto Flex', sans-serif; color:white; margin-top: 280px; margin-left: 30px; margin-right: 30px; margin-bottom: 30px;">28 Aniversario de la UTL</p>
            <v-row class="d-flex align-center mb-2">
              <v-col cols="auto">
                <p class="text-h6" style="color:white; font-family: 'Roboto Flex', sans-serif; margin-left: 30px; margin-right: 0px; margin-top: -8px;">Leer más</p>

              </v-col>
              <v-col cols="auto">
              
                <v-img src="../assets/fondos/carrerastsu/flecha.png" max-height="40px" max-width="40px"></v-img>
                <br>
              </v-col>
            </v-row>
          </v-img>
        </v-card>
      </v-col>
      <v-col cols="12" md="3" class="mx-1 mb-0 pb-0">
        <v-card class="mx-auto pa-0" max-width="400" style="margin-bottom: 0;">
          <v-img
            src="../assets/fondos/noticias2.jpeg"
            height="420px"
            cover
            id="entornosTSU"
          >
            <p class="text-h6 text-left text-weight-bold mb-4" id="textoEntornos" style="font-family: 'Roboto Flex', sans-serif; color:white; margin-top: 280px; margin-left: 30px; margin-right: 30px; margin-bottom: 30px;">28 Aniversario de la UTL</p>
            <v-row class="d-flex align-center mb-2">
              <v-col cols="auto">
                <p class="text-h6" style="color:white; font-family: 'Roboto Flex', sans-serif; margin-left: 30px; margin-right: 0px; margin-top: -8px;">Leer más</p>

              </v-col>
              <v-col cols="auto">
              
                <v-img src="../assets/fondos/carrerastsu/flecha.png" max-height="40px" max-width="40px"></v-img>
                <br>
              </v-col>
            </v-row>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
    
    
         
    
  </div>
</template>
  
  <script>
  
  export default {
    data: () => ({
      
    }),
  };

  
  </script>

<style scoped>
.custom-card {
  position: relative;
  overflow: hidden;
  margin-bottom: 20px; /* Espacio entre los v-card */
}

.custom-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.text-overlay {
  position: absolute;
  top: 90%; /* Ajusta este valor para mover el texto hacia abajo */
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  width: 100%;
  z-index: 1;
  color: white; /* Color del texto */
  background: rgba(0, 0, 0, 0.5); /* Fondo del texto con opacidad */
  padding: 20px; /* Espaciado interno del texto */
}

.custom-text {
  font-family: 'Roboto Flex', sans-serif;
  font-size: 18px; /* Tamaño del texto */
}
.text-overlay {
  /* Estilo para el contenedor principal */
  display: flex;
  align-items: center;
}

.flex-container {
  /* Contenedor interno con estilo de diseño flex */
  display: flex;
  align-items: center;
  margin-left: 50px; /* Ajusta el margen izquierdo según sea necesario */
}
</style>