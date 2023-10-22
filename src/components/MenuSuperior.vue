<template>
    <div>
    <!--#Sección MENU SUPERIOR-->
    <v-app-bar app color="transparent" dark height="100px">
      <div class="d-flex align-center">
        <router-link to="/">
          <v-img
            alt="UTL Logo"
            class="shrink mr-3 mt-4"
            contain
            src="@/assets/Logo_UTL.png"
            transition="scale-transition"
            width="80"
          />
        </router-link>

      </div>

      <v-spacer></v-spacer>

      <!-- Botón de Soy Estudiante -->
      <v-btn text class="white--text"  @click="openDialogSoyEstudiante">
        <v-icon>mdi-account</v-icon>
        
        Soy Estudiante
      </v-btn>
    </v-app-bar>
    </div>
  </template>
  
  <script>
  export default {
    data: () => ({
      
    }),
  };
  </script>
  
