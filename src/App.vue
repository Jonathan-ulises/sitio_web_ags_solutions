<template>
  <v-app>
    <!--#Sección MENU SUPERIOR-->
    <v-app-bar class="elevation-0"
    app
    color="transparent"
    dark
    height="100px"
    hide-on-scroll
    style="position: fixed;"
>
      <div class="d-flex align-center">
        <router-link to="/">
          <v-img
            alt="UTL Logo"
            class="shrink mr-3 mt-4"
            contain
            src="@/assets/LogoUTL_Blanco.png"
            transition="scale-transition"
            width="80"
          />
        </router-link>

        <v-btn
        id="mi-boton"
        plain
        dark
        flat
        class="ml-7 btnmenu"
        href="https://aulavirtual.seg.guanajuato.gob.mx/materias/login/index.php"
        target="_blank"
        elevation="0"
      >
        Aula Virtual
      </v-btn>
      <v-btn
      id="mi-boton"
      plain
      dark
      flat
      class="ml-7 btnmenu"
      href="https://www.microsoft.com/es-mx/microsoft-365/outlook/email-and-calendar-software-microsoft-outlook"
      target="_blank"
      elevation="0"
    >
      Correo Electrónico
    </v-btn>

    <v-btn
    id="mi-boton"
    plain
    dark
    flat
    class="ml-7 btnmenu"
    href="https://sito.utleon.edu.mx/"
    target="_blank"
    elevation="0"
  >
    SITO
  </v-btn>
  <v-btn
  id="mi-boton"
  plain
  dark
  flat
  class="ml-7 btnmenu"
  href="http://www.bibliotecaecest.mx/"
  target="_blank"
  elevation="0"
>
  Biblioteca Digital
</v-btn>
      <v-btn
        id="mi-boton"
        plain
        dark
        flat
        class="ml-7 btnmenu"
        href="https://www.utleon.edu.mx/resource/img/CALENDARIO%20LE%C3%93N.jpg"
        target="_blank"
        elevation="0"
      >
        Calendario Escolar
      </v-btn>

      </div>

      <v-spacer></v-spacer>

      <!-- Botón de Soy Estudiante -->
      <v-btn text class="white--text"  @click="openDialogSoyEstudiante">
        <v-icon>mdi-menu</v-icon>
        
      Menú
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
    </v-row >
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
          :src="dialog_soy_estudiante == true && sub_menu_soy_estudiante_tramites == true ? require('@/assets/fondos/SoyEstudiante.png') :
          dialog_soy_estudiante == true && sub_menu_soy_aspirante_oferta_educativa == true ? require('@/assets/fondos/SoyEstudiante.png') :
          dialog_soy_estudiante == true && sub_menu_soy_aspirante == true ? require('@/assets/fondos/fondo_aspirante.png') :
          dialog_soy_estudiante == true && sub_menu_soy_estudiante == true ? require('@/assets/fondos/oferta.png') :
          dialog_soy_estudiante == true && sub_menu_soy_docente == true ? require('@/assets/fondos/fondo_tramites.png') :
          require('@/assets/fondos/FondoMenuPrincipal.png')"
          
          
          style="height:720px;"
        >
          <!-- AQUI EMPIEZA LA BARRA DE HASTA ARRIBA SECCION SOY ESTUDIANTE-->
          
          <template>
            <v-toolbar dark color="#00FF0000" class="elevation-0">
              <v-row align="center" class="d-flex">
                <v-img
                  src="@/assets/LogoUTL_Blanco.png"
                  max-height="60"
                  max-width="60"
                  class="mr-6"
                ></v-img>
                <v-btn
        id="mi-boton"
        plain
        dark
        flat
        class="ml-7 btnmenu"
        href="https://aulavirtual.seg.guanajuato.gob.mx/materias/login/index.php"
        target="_blank"
        elevation="0"
      >
        Aula Virtual
      </v-btn>
                <v-btn
                id="mi-boton"
                plain
                dark
                flat
                class="ml-7 btnmenu"
                href="https://www.utleon.edu.mx/resource/img/CALENDARIO%20LE%C3%93N.jpg"
                target="_blank"
                elevation="0"
              >
                Calendario Escolar
              </v-btn>

              <v-btn
              id="mi-boton"
              plain
              dark
              flat
              class="ml-7 btnmenu"
              href="https://www.microsoft.com/es-mx/microsoft-365/outlook/email-and-calendar-software-microsoft-outlook"
              target="_blank"
              elevation="0"
            >
              Correo Electrónico
            </v-btn>

            <v-btn
            id="mi-boton"
            plain
            dark
            flat
            class="ml-7 btnmenu"
            href="https://sito.utleon.edu.mx/"
            target="_blank"
            elevation="0"
          >
          SITO
          </v-btn>

          <v-btn
          id="mi-boton"
          plain
          dark
          flat
          class="ml-7 btnmenu"
          href="http://www.bibliotecaecest.mx/"
          target="_blank"
          elevation="0"
        >
          Biblioteca Digital
        </v-btn>

                <v-spacer></v-spacer>

                <v-btn icon dark @click="fnLimpiar">
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                    @click="
                    fnMostrarMenu('sub_menu_soy_aspirante_oferta_educativa')
                  "
                  >
                    Oferta Educativa
                  </v-btn>
                </v-list-item>
                <v-list-item class="ma-0 pa-0">
                  <v-btn
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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

             <!--SECCION SOY ESTUDIANTE / TRAMITES-->
             <v-list
             v-if="sub_menu_soy_estudiante_tramites"
             class="ma-0 pa-0"
             color="#00FF0000"
           >
             <v-list-item class="ma-0 pa-0">
              <router-link to="solicitud-constancias" style="text-decoration: none; color: inherit;">
               <v-btn
               id="mi-boton"
               plain
               dark
               flat
               class="ml-7 btnmenu"
               target="_blank"
               elevation="0"
                 style="
                   all: initial;
                   font-size: 20px;
                   height: 50px;
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
                 @click=fnCerrarDialog
               >
                 Solicitud de Constancias
               </v-btn>
              </router-link>
             </v-list-item>
             <v-list-item class="ma-0 pa-0">
               <v-btn
               id="mi-boton"
               plain
               dark
               flat
               class="ml-7 btnmenu"
               target="_blank"
               elevation="0"
                 style="
                   all: initial;
                   font-size: 20px;
                   height: 50px;
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
               id="mi-boton"
               plain
               dark
               flat
               class="ml-7 btnmenu"
               target="_blank"
               elevation="0"
                 style="
                   all: initial;
                   font-size: 20px;
                   height: 50px;
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
                 Trámite estudiantil IMSS
               </v-btn>
             </v-list-item>
             <v-list-item class="ma-0 pa-0">
               <v-btn
               id="mi-boton"
               plain
               dark
               flat
               class="ml-7 btnmenu"
               target="_blank"
               elevation="0"
                 style="
                   all: initial;
                   font-size: 20px;
                   height: 50px;
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
                 Becas
               </v-btn>
             </v-list-item>
             <v-list-item class="ma-0 pa-0">
               <v-btn
               id="mi-boton"
               plain
               dark
               flat
               class="ml-7 btnmenu"
               target="_blank"
               elevation="0"
                 style="
                   all: initial;
                   font-size: 20px;
                   height: 50px;
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
            Pago de examen de regularización

            </v-btn>
             </v-list-item>
             <v-list-item class="ma-0 pa-0">
               <v-btn
               id="mi-boton"
               plain
               dark
               flat
               class="ml-7 btnmenu"
               target="_blank"
               elevation="0"
                 style="
                   all: initial;
                   font-size: 20px;
                   height: 50px;
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
            Reinscripción

            </v-btn>
             </v-list-item>
             <v-list-item class="ma-0 pa-0">
               <v-btn
               id="mi-boton"
               plain
               dark
               flat
               class="ml-7 btnmenu"
               target="_blank"
               elevation="0"
                 style="
                   all: initial;
                   font-size: 20px;
                   height: 50px;
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
            Reingreso

            </v-btn>
             </v-list-item>
             
            
             
           </v-list>


               <!--SECCION SOY ASPIRANTE / OFERTA EDUCATIVA-->
               <v-list
               v-if="sub_menu_soy_aspirante_oferta_educativa"
               class="ma-0 pa-0"
               color="#00FF0000"
             >
               <v-list-item class="ma-0 pa-0">
                <router-link to="carreras-tsu" style="text-decoration: none; color: inherit;">
                 <v-btn
                 id="mi-boton"
                 plain
                 dark
                 flat
                 class="ml-7 btnmenu"
                 target="_blank"
                 elevation="0"
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 50px;
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
                   @click="fnLimpiar"
                 >
                   Carreras TSU
                 </v-btn>
                </router-link>
               </v-list-item>
               <v-list-item class="ma-0 pa-0">
                <router-link to="/carreras-ing" style="text-decoration: none; color: inherit;">
                 <v-btn
                 id="mi-boton"
                 plain
                 dark
                 flat
                 class="ml-7 btnmenu"
                 target="_blank"
                 elevation="0"
                   style="
                     all: initial;
                     font-size: 20px;
                     height: 50px;
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
                   @click="fnLimpiar"
                 >
                   Carreras Licenciatura
                 </v-btn>
                </router-link>
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                  id="mi-boton"
                  plain
                  dark
                  flat
                  class="ml-7 btnmenu"
                  target="_blank"
                  elevation="0"
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
                class="white--text transparent-button ml-7"
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

            <router-link to="/">
              <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-7"
              @click="fnMostrarMensajeInstitucional"
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
              class="white--text transparent-button ml-7"
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
           
            <router-link to="transparencia-utl">
              <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-7"
              @click=fnCerrarDialog
              elevation="0"
              style="
                border: none;
                font-family: 'Roboto Flex', sans-serif;
                font-weight: bold;
              "
              >
              Transparencia
              </v-btn>
            </router-link>
            <router-link to="utl-cifras">
            <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-7"
              @click=fnCerrarDialog
              elevation="0"
              style="
                border: none;
                font-family: 'Roboto Flex', sans-serif;
                font-weight: bold;
              "

            >
              UTL en cifras
            </v-btn>
          </router-link>

            <v-btn
              color="#00FF0000"
              class="white--text transparent-button ml-7"
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
              class="white--text transparent-button ml-7"
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

  <br>
  <br>
  <br>
 
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
    sub_menu_soy_aspirante_oferta_educativa: false
 

    //
  }),
  methods: {
    fnMostrarMensajeInstitucional() {
      this.dialog_soy_estudiante = false;
      window.scrollTo(0, document.body.scrollHeight * 0.3);
    },
    fnLimpiar() {
    this.sub_menu_soy_estudiante= false;
    this.sub_menu_soy_docente= false;
    this.sub_menu_soy_estudiante_tramites= false;
    this.sub_menu_soy_estudiante_tramites_bajas= false;
    this.sub_menu_soy_aspirante= false;
    this.dialog_soy_estudiante = false;
    this.sub_menu_soy_aspirante_oferta_educativa = false;
    },
    fnLimpiarVariables() {
    this.sub_menu_soy_estudiante= false;
    this.sub_menu_soy_docente= false;
    this.sub_menu_soy_estudiante_tramites= false;
    this.sub_menu_soy_estudiante_tramites_bajas= false;
    this.sub_menu_soy_aspirante= false;
    this.sub_menu_soy_aspirante_oferta_educativa = false;
    },
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

        this.sub_menu_soy_docente= false;
    this.sub_menu_soy_estudiante_tramites= false;
    this.sub_menu_soy_estudiante_tramites_bajas= false;
    this.sub_menu_soy_aspirante= false;
    this.sub_menu_soy_aspirante_oferta_educativa = false;

        if (this.sub_menu_soy_estudiante == true) {
          this.sub_menu_soy_estudiante = false;
        } else {
          this.sub_menu_soy_estudiante = true;

        }
      }
      if (this.menu_encender == "sub_menu_soy_aspirante") {
        this.sub_menu_soy_estudiante= false;
    this.sub_menu_soy_docente= false;
    this.sub_menu_soy_estudiante_tramites= false;
    this.sub_menu_soy_estudiante_tramites_bajas= false;
    this.sub_menu_soy_aspirante_oferta_educativa = false;

        

        if (this.sub_menu_soy_aspirante == true) {
          this.sub_menu_soy_aspirante = false;
        } else {
          this.sub_menu_soy_aspirante = true;
        }
      }

      if (this.menu_encender == "sub_menu_soy_docente") {
        this.sub_menu_soy_estudiante= false;
    this.sub_menu_soy_estudiante_tramites= false;
    this.sub_menu_soy_estudiante_tramites_bajas= false;
    this.sub_menu_soy_aspirante= false;
    this.sub_menu_soy_aspirante_oferta_educativa = false;



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


      if (this.menu_encender == "sub_menu_soy_aspirante_oferta_educativa") {
        if (this.sub_menu_soy_aspirante_oferta_educativa == true) {
          this.sub_menu_soy_aspirante_oferta_educativa = false;
        } else {
          this.sub_menu_soy_aspirante_oferta_educativa = true;
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
.btnmenu {
  color: white !important; /* Establece el color del texto como blanco y utiliza !important para asegurar prioridad */
  text-decoration: none; /* Elimina cualquier decoración de texto predeterminada */
  background-color: transparent; /* Establece el fondo como transparente */
  border: none; /* Elimina el borde del botón */
  font-family: 'Roboto Flex', sans-serif;
  font-weight: bold;
  cursor: pointer;
}
.btnmenu:after {
  background: #fff;
  content: "";
  display: block;
  height: 2px;
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  transition: width 0.3s ease 0s;
}

.btnmenu:hover:after {
  width: 100%;
}

</style>
