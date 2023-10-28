<template>
    <div>
      <div>
    <v-img src="../assets/fondos/transparencia.png" max-height with cover aspect-ratio="16/9">
      <p class="text-h1 text-start font-weight-class" style="color:#00B394; font-family: 'Roboto Flex', sans-serif;font-weight: bold; margin-top: 200px; margin-bottom: 100px;">Transparencia</p>
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
    </div>
  </template>

  <style>
  
  .elemento:hover{
    transform: scale(1.2);
  }

  .elemento{
    transition: 1s;
    
  }

  </style>