<template>
  <v-app>

    <v-carousel cycle height="747" hide-delimiters :next-icon="null" :prev-icon="null">
      <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade-transition"
        transition="fade-transition"
      ></v-carousel-item>
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
    <v-main>
      <template>
        
       
      </template>
      <router-view />
    </v-main>
    <v-row justify="center">
      <v-dialog
        v-model="dialog_menu"
        fullscreen
        hide-overlay
        transition="dialog-top-transition"
      >
      </v-dialog>

      <!--Seccion Menu-->
    </v-row>
    <v-row justify="center">
      <v-dialog
        v-model="dialog_soy_estudiante"
        fullscreen
        hide-overlay
        transition="dialog-top-transition"
      >
      <!--IMAGENES DE FONDO-->
        <v-card color="#00FF0000">

          <v-img
          :src="dialog_soy_estudiante == true && sub_menu_soy_estudiante == true ? require('@/assets/fondos/fondo_estudiante.jpeg') : (dialog_soy_estudiante == true && sub_menu_soy_aspirante == true ? require('@/assets/fondos/fondo_aspirante.jpeg') : require('@/assets/fondos/fondo_defecto.jpeg'))"
          
          style="height:750px"
        >

          <!-- AQUI EMPIEZA LA BARRA DE HASTA ARRIBA SECCION SOY ESTUDIANTE-->

          <template>
            <v-toolbar dark color="#00FF0000">
              <v-row align="center" class="d-flex">
                <v-img
                  src="@/assets/Logo_UTL.png"
                  max-height="60"
                  max-width="60"
                  class="mr-6"
                ></v-img>
                <v-btn
                  color="#00FF0000"
                  class="white-text transparent-button"
                  href="https://aulavirtual.seg.guanajuato.gob.mx/materias/login/index.php"
                  target="_blank"
                  elevation="0"
                  style="
                    border: none;
                    font-family: 'Roboto Flex', sans-serif;
                    font-weight: bold;
                  "
                >
                  Aula Virtual
                </v-btn>
                <v-btn
                  color="#00FF0000"
                  class="white-text transparent-button"
                  href="https://www.utleon.edu.mx/resource/img/CALENDARIO%20LE%C3%93N__.jpg"
                  target="_blank"
                  elevation="0"
                  style="
                    border: none;
                    font-family: 'Roboto Flex', sans-serif;
                    font-weight: bold;
                  "
                >
                  Calendario Escolar
                </v-btn>

                <v-btn
                  color="#00FF0000"
                  class="white-text transparent-button"
                  elevation="0"
                  style="
                    border: none;
                    font-family: 'Roboto Flex', sans-serif;
                    font-weight: bold;
                  "
                  href="https://login.live.com/login.srf?wa=wsignin1.0&rpsnv=16&ct=1697739439&rver=7.0.6738.0&wp=MBI_SSL&wreply=https%3a%2f%2foutlook.live.com%2fowa%2f%3fnlp%3d1%26cobrandid%3dab0455a0-8d03-46b9-b18b-df2f57b9e44c%26RpsCsrfState%3dd9cb0b76-b115-cfb0-0a2c-26012db8721d&id=292841&aadredir=1&CBCXT=out&lw=1&fl=dob%2cflname%2cwld&cobrandid=ab0455a0-8d03-46b9-b18b-df2f57b9e44c"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  Correo Electrónico
                </v-btn>

                <v-btn
                  color="#00FF0000"
                  class="transparent-button"
                  elevation="0"
                  style="
                    border: none;
                    font-family: 'Roboto Flex', sans-serif;
                    font-weight: bold;
                  "
                >
                  <a
                    href="https://sito.utleon.edu.mx/"
                    class="white-text"
                    style="text-decoration: none; color: white"
                  >
                    SITO
                  </a>
                </v-btn>

                <v-btn
                  color="#00FF0000"
                  class="white-text transparent-button"
                  elevation="0"
                  style="
                    border: none;
                    font-family: 'Roboto Flex', sans-serif;
                    font-weight: bold;
                  "
                  @click="redirectTo('biblioteca-digital')"
                  href="https://sibisut.utleon.edu.mx/Descargar/Bidig2020.pdf"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  Biblioteca Digital
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn icon dark @click="dialog_soy_estudiante = false">
                  <v-row align="center">
                    <v-col
                      class="d-flex align-center"
                      style="margin-right: 30px"
                    >
                   
                    <div style="display: flex; align-items: center; justify-content: flex-end; margin-right: 70px;">
                      <span style="margin-right: 10px;">Cerrar</span>
                      <v-icon color="white" class="circle-icon">mdi-close</v-icon>
                    </div>

                    </v-col>
                  </v-row>
                </v-btn>
              </v-row>
            </v-toolbar>
          </template>

          <v-row>
            <v-col md="3" class="ml-7">
              <!--COLUMNA SUBMENU 1 -->

              <v-list color="#00FF0000" class="ma-0 pa-0 compact-list">
                <v-list-item class="ma-0 pa-0 compact-list text-center">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="fnMostrarMenu('sub_menu_soy_estudiante')"
                  >
                    Soy Estudiante
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0 compact-list text-center">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="fnMostrarMenu('sub_menu_soy_docente')"
                  >
                    Soy Docente
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0 compact-list text-center">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('noticias')"
                  >
                    Soy Administrativo
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0 compact-list text-center">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="fnMostrarMenu('sub_menu_soy_aspirante')"

                  >
                    Soy Aspirante
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0 compact-list text-center">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('utl-en-cifras')"
                  >
                    Soy Egresado
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0 compact-list text-center">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('normativa')"
                  >
                    Soy Empresario
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0 compact-list text-center">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('trabajar-en-utl')"
                  >
                    Somos Utl
                  </v-btn>
                </v-list-item>
              </v-list>
            </v-col>
            <v-col md="3">

              <!--COLUMNA SUBMENU 2 -->

              <!--SECCION SOY ESTUDIANTE-->
              <v-list
                v-if="sub_menu_soy_estudiante"
                class="ma-0 pa-0"
                color="#00FF0000"
              >
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="fnMostrarMenu('sub_menu_soy_estudiante_tramites')"
                  >
                    Trámites
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('mensaje-institucional')"
                  >
                    Servicios
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('noticias')"
                  >
                    Organos
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('transparencia')"
                  >
                    Normativa Estudiantil
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('utl-en-cifras')"
                  >
                    Quejas
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('normativa')"
                  >
                    Contacto
                  </v-btn>
                </v-list-item>
              </v-list>

              <!--SECCION SOY DOCENTE-->

              <v-list
                v-if="sub_menu_soy_docente"
                class="ma-0 pa-0"
                color="#00FF0000"
              >
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('quienes-somos')"
                  >
                    Recursos para la gestión
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('mensaje-institucional')"
                  >
                    Normativa
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('noticias')"
                  >
                    Desarrollo Académico
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('transparencia')"
                  >
                    Investigación UTL
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('utl-en-cifras')"
                  >
                    Salud Integral
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('normativa')"
                  >
                    Órganos Colegiados
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('normativa')"
                  >
                    Contáctanos
                  </v-btn>
                </v-list-item>
              </v-list>

                <!--SECCION SOY ASPIRANTE-->

                <v-list
                v-if="sub_menu_soy_aspirante"
                class="ma-0 pa-0"
                color="#00FF0000"
              >
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('quienes-somos')"
                  >
                    Conoce la UTL
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('mensaje-institucional')"
                  >
                    Oferta Educativa
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('noticias')"
                  >
                    Como estudiar en la UTL
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('transparencia')"
                  >
                    Contactanos
                  </v-btn>
                </v-list-item>
               
              </v-list>

            </v-col>

            <v-col md="3">
              <!--COLUMNA SUBMENU 3 -->
              <!--SECCION SOY ESTUDIANTE / TRAMITES-->
              <v-list
                v-if="sub_menu_soy_estudiante_tramites"
                class="ma-0 pa-0"
                color="#00FF0000"
              >
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('quienes-somos')"
                  >
                    Solicitud de Constancias
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('mensaje-institucional')"
                  >
                    Trámite de Credencial
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('noticias')"
                  >
                    Trámite Estudiantil IMSS
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('transparencia')"
                  >
                    Becas
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('utl-en-cifras')"
                  >
                    Pago de Examen de Regularización
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('normativa')"
                  >
                    Reinscripción
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('normativa')"
                  >
                    Reingreso
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="
                      fnMostrarMenu('sub_menu_soy_estudiante_tramites_bajas')
                    "
                  >
                    Trámite de Baja
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 20px;
                      height: 70px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('normativa')"
                  >
                    Titulación
                  </v-btn>
                </v-list-item>
              </v-list>

               <!--SECCION SOY ASPIRANTE / OFERTA EDUCATIVA-->
               <v-list
               v-if="sub_menu_soy_estudiante_tramites"
               class="ma-0 pa-0"
               color="#00FF0000"
             >
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="redirectTo('quienes-somos')"
                 >
                   Solicitud de Constancias
                 </v-btn>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="redirectTo('mensaje-institucional')"
                 >
                   Trámite de Credencial
                 </v-btn>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="redirectTo('noticias')"
                 >
                   Trámite Estudiantil IMSS
                 </v-btn>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="redirectTo('transparencia')"
                 >
                   Becas
                 </v-btn>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="redirectTo('utl-en-cifras')"
                 >
                   Pago de Examen de Regularización
                 </v-btn>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="redirectTo('normativa')"
                 >
                   Reinscripción
                 </v-btn>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="redirectTo('normativa')"
                 >
                   Reingreso
                 </v-btn>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="
                     fnMostrarMenu('sub_menu_soy_estudiante_tramites_bajas')
                   "
                 >
                   Trámite de Baja
                 </v-btn>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                 <v-btn
                   dark
                   flat
                   text
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 70px;
                     width: 100%;
                     text-align: left;
                     color: white;
                     padding-left: 10px;
                     padding-right: 10px;
                     font-family: 'Roboto Flex', sans-serif;
                     letter-spacing: 2px;
                     line-height: 1.5;
                     font-weight: bold;
                   "
                   @click="redirectTo('normativa')"
                 >
                   Titulación
                 </v-btn>
               </v-list-item>
             </v-list>
            </v-col>

            <v-col md="3">
              <!--COLUMNA SUBMENU 4 -->

              <!--SECCION SOY ESTUDIANTE / TRAMITES / BAJAS -->
              <v-list
                v-if="sub_menu_soy_estudiante_tramites_bajas"
                class="ma-0 pa-0"
                color="#00FF0000"
              >
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flatnt-s
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('quienes-somos')"
                  >
                    Baja Temporal
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                    dark
                    flat
                    text
                    style="
                      all: initial;
                      font-size: 24px;
                      height: 85px;
                      width: 100%;
                      text-align: left;
                      color: white;
                      padding-left: 10px;
                      padding-right: 10px;
                      font-family: 'Roboto Flex', sans-serif;
                      letter-spacing: 2px;
                      line-height: 1.5;
                      font-weight: bold;
                    "
                    @click="redirectTo('mensaje-institucional')"
                  >
                    Baja Definitiva
                  </v-btn>
                </v-list-item>
              </v-list>

              
            </v-col>
          </v-row>
          <v-footer color="#00FF0000">
            <router-link to="/quienes-somos">
              <v-btn
                color="#00FF0000"
                class="white--text transparent-button ml-8"
                @click="fnCerrarDialog"
                elevation="0"
                style="
                  border: none;
                  font-family: 'Roboto Flex', sans-serif;
                  font-weight: bold;
                "
              >
                ¿Quienes somos?
              </v-btn>
            </router-link>

            <router-link to="/mensaje-institucional">
              <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-8"
              @click="redirectTo('calendario-escolar')"
              elevation="0"
              style="
                border: none;
                font-family: 'Roboto Flex', sans-serif;
                font-weight: bold;
              "
            >
              Mensaje Institucional
            </v-btn>
            </router-link>
       

            <router-link>
              <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-8"
              @click="redirectTo('correo-electronico')"
              elevation="0"
              style="
                border: none;
                font-family: 'Roboto Flex', sans-serif;
                font-weight: bold;
              "
            >
              Noticias
            </v-btn>
            </router-link>
           

            <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-8"
              @click="redirectTo('sitio')"
              elevation="0"
              style="
                border: none;
                font-family: 'Roboto Flex', sans-serif;
                font-weight: bold;
              "
            >
              Transparencia
            </v-btn>

            <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-8"
              @click="redirectTo('biblioteca-digital')"
              elevation="0"
              style="
                border: none;
                font-family: 'Roboto Flex', sans-serif;
                font-weight: bold;
              "
            >
              UTL en cifras
            </v-btn>

            <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-8"
              @click="redirectTo('biblioteca-digital')"
              elevation="0"
              style="
                border: none;
                font-family: 'Roboto Flex', sans-serif;
                font-weight: bold;
              "
            >
              Normativa
            </v-btn>

            <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-8"
              @click="redirectTo('biblioteca-digital')"
              elevation="0"
              style="
                border: none;
                font-family: 'Roboto Flex', sans-serif;
                font-weight: bold;
              "
            >
              ¿Quieres trabajar en la UTL?
            </v-btn>
          </v-footer>

          
          </v-img>
        </v-card>
      </v-dialog>
    </v-row>
  </v-carousel>
  <br>
  <br>
  <br>
  <card>
    <v-row>
      <v-col md="1"></v-col>
      <v-col md="4">
        <br>
        <br>
        <br>
            <p style="text-align: justify; font-family: 'Roboto', sans-serif; font-weight: 600; font-size: 16px;">
              Es un gusto muy especial dirigirme a todas y todos los integrantes de la Comunidad UTL: estudiantado, personal docente y administrativo, y demás plantilla actoral de nuestro entorno universitario.

Desde marzo ya estamos de regreso a casa. Y en este deseo de normalizar nuestra vida universitaria, hemos vivenciado un proceso necesario de reencuentro, de reconocimiento, para compensar esos meses de confinamiento que afectaron nuestra forma de relacionarnos personal y colectivamente. Pero si algo nos define, es que somos una institución tecnológicamente humana, en innovación y adaptación constante.

Y en esta nueva realidad, que nos enfocamos en dar prioridad a la salud, atendiendo en todo momento a las medidas sanitarias para mantener a raya todo contagio. Además, es necesario, como dice nuestro Gobernador Diego Sinhué Rodríguez, reinventarnos para ser mejores, esto es, crear nuevas formas de realizar el proceso formativo, académico, administrativo para que nuestra UTL siga siendo considerada un bastión importante del ecosistema educativo guanajuatense.

Como bien lo dice nuestro lema “Somos Leones, Somos Leonas”, les invito a construir entre todos una “guarida segura” donde prevalezca un ambiente de colaboración y convivencia, donde nos sintamos a gusto en “nuestra guarida”, promoviendo una cultura de paz y de respeto a nuestros derechos humanos fundamentales. Acorde a los nuevos tiempos, mostremos a la sociedad que la UTL es íntegra, inclusiva y sostenible.
            </p>
      </v-col>
      <v-col md="5">
        <br>
        <br>
        <br>
        <img src="@/assets/rectora.png" alt="Yoloxóchitl Bustamante Díez" style="margin-left: 100px; width: 110%">
        <h1 style="margin-left: 27%"> 
          Yoloxóchitl Bustamante Díez
        </h1>
        <p style="margin-left: 52%">
           
          Encargada de despacho de Rectoría
        </p>
   </v-col>
    </v-row>
  </card>
  </v-app>
</template>

<script>
import "./plugins/estilos.css";

export default {
  name: "App",

  data: () => ({
    dialog_menu: false,
    dialog_soy_estudiante: false,
    notifications: false,
    sound: false,
    widgets: false,
    menu_encender: "",
    sub_menu_soy_estudiante: false,
    sub_menu_soy_docente: false,
    sub_menu_soy_estudiante_tramites: false,
    sub_menu_soy_estudiante_tramites_bajas: false,
    sub_menu_soy_aspirante: false,
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

    //
  }),
  methods: {
    fnLimpiar() {},
    openDialogMenu() {
      this.dialog_menu = true;
    },
    fnCerrarDialog() {
      this.dialog_soy_estudiante = false;
    },
    openDialogSoyEstudiante() {
      this.dialog_soy_estudiante = true;
    },
    redirectTo(section) {
      // Lógica para redireccionar a la sección correspondiente
      console.log(`Redireccionar a: ${section}`);
    },
    fnMostrarMenu(section) {
      //Limpiar Variables

      // this.menu_encender = '';

      //Termina Limpiar Variables

      this.menu_encender = section;

      //Submenu 2
      if (this.menu_encender == "sub_menu_soy_estudiante") {
        this.sub_menu_soy_docente = false;
        this.sub_menu_soy_estudiante_tramites = false;
        this.sub_menu_soy_estudiante_tramites_bajas = false;
        this.sub_menu_soy_aspirante = false;

        if (this.sub_menu_soy_estudiante == true) {
          this.sub_menu_soy_estudiante = false;
        } else {
          this.sub_menu_soy_estudiante = true;

        }
      }
      if (this.menu_encender == "sub_menu_soy_aspirante") {
        this.sub_menu_soy_docente = false;
        this.sub_menu_soy_estudiante_tramites = false;
        this.sub_menu_soy_estudiante_tramites_bajas = false;
        

        if (this.sub_menu_soy_aspirante == true) {
          this.sub_menu_soy_aspirante = false;
        } else {
          this.sub_menu_soy_aspirante = true;
        }
      }

      if (this.menu_encender == "sub_menu_soy_docente") {
        this.sub_menu_soy_estudiante = false;
        this.sub_menu_soy_estudiante_tramites = false;
        this.sub_menu_soy_aspirante = false;


        if (this.sub_menu_soy_docente == true) {
          this.sub_menu_soy_docente = false;
        } else {
          this.sub_menu_soy_docente = true;
        }
      }

      // Submenu 3

      if (this.menu_encender == "sub_menu_soy_estudiante_tramites") {
        if (this.sub_menu_soy_estudiante_tramites == true) {
          this.sub_menu_soy_estudiante_tramites = false;
        } else {
          this.sub_menu_soy_estudiante_tramites = true;
        }
      }

      // Submenu 4

      if (this.menu_encender == "sub_menu_soy_estudiante_tramites_bajas") {
        if (this.sub_menu_soy_estudiante_tramites_bajas == true) {
          this.sub_menu_soy_estudiante_tramites_bajas = false;
        } else {
          this.sub_menu_soy_estudiante_tramites_bajas = true;
        }
      }
      

      console.log(section);

      //console.log(`Redireccionar a: ${section}`);
    },
  },
};
</script>
<style>
.boton_diana {
  all: initial;
  font-size: 24px;
  height: 85px;
  width: 100%;
  text-align: left;
  color: white;
  padding-left: 10px;
  padding-right: 10px;
  font-family: 'Roboto Flex', sans-serif;
  letter-spacing: 2px;
  line-height: 1.5;
  font-weight: bold;
}
</style>
