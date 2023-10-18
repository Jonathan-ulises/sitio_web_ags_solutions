<template>
  <v-app>
    <v-app-bar
      app
      color="transparent"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="@/assets/Logo_UTL.png" 
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />

        <!-- Campo de texto de búsqueda con ícono -->
        <v-text-field
          label="Buscar"
          prepend-inner-icon="mdi-magnify"
          class="mr-4"
        />
      </div>

      <v-spacer></v-spacer>

      <!-- Botón de Soy Estudiante -->
      <v-btn text class="black--text" @click="openDialogSoyEstudiante">
        <v-icon>mdi-account</v-icon>

        Soy Estudiante
      </v-btn>
    </v-app-bar>
    <v-main>
      <router-view/>

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
  <v-row justify="center" >
    <v-dialog
      v-model="dialog_soy_estudiante"
      fullscreen
      hide-overlay
      transition="dialog-top-transition"
      
    >
      <v-card>
        <!-- AQUI EMPIEZA LA BARRA DE HASTA ARRIBA SECCION SOY ESTUDIANTE-->

        <v-toolbar
          dark
          color="#0C398C" 
        >
         <v-img src="@/assets/Logo_UTL.png" max-height="40" max-width="40"></v-img>
          <v-spacer></v-spacer>
            
            <v-btn icon dark @click="dialog_soy_estudiante = false">
          <v-row align="center" justify="end">
            <v-col class="d-flex align-center" style="margin-right: 30px;">
              <span>Cerrar</span>
              <v-icon color="green" class="circle-icon" style="margin-left: 5px;">
                mdi-close
              </v-icon>
            </v-col>
          </v-row>
          </v-btn>
        
        </v-toolbar>
        <v-row>
<v-col md="3">
  <!--COLUMNA SUBMENU 1 -->

    <v-list class="ma-0 pa-0 compact-list">
      <v-list-item class="ma-0 pa-0 compact-list">
        <v-btn style="font-size: 18px; height: 85px; width: 100%;" @click="fnMostrarMenu('sub_menu_soy_estudiante')">¿Soy Estudiante?</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn  style="font-size: 18px; height: 85px; width: 100%;" @click="fnMostrarMenu('sub_menu_soy_docente')">¿Soy Docente?</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 85px; width: 100%;" @click="redirectTo('noticias')">¿Soy Administrativo?</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 85px; width: 100%;" @click="redirectTo('transparencia')">¿Soy Aspirante?</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 85px; width: 100%;" @click="redirectTo('utl-en-cifras')">¿Soy Egresado?</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 85px; width: 100%;" @click="redirectTo('normativa')">¿Soy Empresario?</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 85px; width: 100%;" @click="redirectTo('trabajar-en-utl')">¿Somos Utl?</v-btn>
      </v-list-item>
    </v-list>
</v-col>
<v-col md="3">
    <!--COLUMNA SUBMENU 2 -->

            <!--SECCION SOY ESTUDIANTE-->
    <v-list v-if="sub_menu_soy_estudiante" v-list class="ma-0 pa-0">
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="fnMostrarMenu('sub_menu_soy_estudiante_tramites')">Trámites</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('mensaje-institucional')">Servicios</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('noticias')">Organos</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('transparencia')">Normativa Estudiantil</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('utl-en-cifras')">Quejas</v-btn>
      </v-list-item>
      <v-list-item class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('normativa')">Contacto</v-btn>
      </v-list-item>
    </v-list>
 
    <!--SECCION SOY DOCENTE-->

    <v-list v-if="sub_menu_soy_docente" v-list class="ma-0 pa-0">
      <v-list-item v-list class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('quienes-somos')">Recursos para la gestión</v-btn>
      </v-list-item>
      <v-list-item v-list class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('mensaje-institucional')">Normativa</v-btn>
      </v-list-item>
      <v-list-item v-list class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('noticias')">Desarrollo Académico</v-btn>
      </v-list-item>
      <v-list-item v-list class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('transparencia')">Investigación UTL</v-btn>
      </v-list-item>
      <v-list-item v-list class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('utl-en-cifras')">Salud Integral</v-btn>
      </v-list-item>
      <v-list-item v-list class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('normativa')">Órganos Colegiados</v-btn>
      </v-list-item>
      <v-list-item v-list class="ma-0 pa-0">
        <v-btn style="font-size: 18px; height: 80px; width: 100%;" @click="redirectTo('normativa')">Contactanos</v-btn>
      </v-list-item>

    </v-list>
</v-col>

<v-col md="3">
  <!--COLUMNA SUBMENU 3 -->
          <!--SECCION SOY ESTUDIANTE / TRAMITES-->
  <v-list v-if="sub_menu_soy_estudiante_tramites" v-list class="ma-0 pa-0">
    <v-list-item class="ma-0 pa-0">
      <v-btn  style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('quienes-somos')">Solicitud de Constancias</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('mensaje-institucional')">Trámite de Credencial</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('noticias')">Trámite Estudiantil IMSS</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('transparencia')">Becas</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 17px; height: 70px; width: 100%;" @click="redirectTo('utl-en-cifras')">Pago de Examen de Regularización</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('normativa')">Reinscripción</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('normativa')">Reingreso</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="fnMostrarMenu('sub_menu_soy_estudiante_tramites_bajas')">Trámite de Baja</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('normativa')">Titulación</v-btn>
    </v-list-item>
  </v-list>
</v-col>

<v-col md="3">
  <!--COLUMNA SUBMENU 4 -->

          <!--SECCION SOY ESTUDIANTE / TRAMITES / BAJAS -->
  <v-list v-if="sub_menu_soy_estudiante_tramites_bajas" class="ma-0 pa-0">
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('quienes-somos')">Baja Temporal</v-btn>
    </v-list-item>
    <v-list-item class="ma-0 pa-0">
      <v-btn style="font-size: 18px; height: 70px; width: 100%;" @click="redirectTo('mensaje-institucional')">Baja Definitiva</v-btn>
    </v-list-item>
   
  </v-list>
</v-col>
        </v-row>

      </v-card>
    </v-dialog>
  </v-row>
  

  </v-app>
</template>

<script>

import './plugins/estilos.css';


export default {

  name: 'App',

  data: () => ({
   
        dialog_menu: false,
        dialog_soy_estudiante: false,
        notifications: false,
        sound: false,
        widgets: false,
        menu_encender : '',
        sub_menu_soy_estudiante : false,
        sub_menu_soy_docente : false,
        sub_menu_soy_estudiante_tramites: false,
        sub_menu_soy_estudiante_tramites_bajas: false
      
    //
  }),

  methods: {
     fnLimpiar(){
      
    },
    openDialogMenu() {
      this.dialog_menu = true;
    },
    fnCerrarDialog() {
      this.dialog_menu = false;
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
      if(this.menu_encender == 'sub_menu_soy_estudiante'){
        this.sub_menu_soy_docente = false;
        this.sub_menu_soy_estudiante_tramites = false;
        this.sub_menu_soy_estudiante_tramites_bajas = false;

        if(this.sub_menu_soy_estudiante == true){
          this.sub_menu_soy_estudiante = false;
        }else{
          this.sub_menu_soy_estudiante = true;
             
        }
      }

      if(this.menu_encender == 'sub_menu_soy_docente'){
        this.sub_menu_soy_estudiante = false;
        this.sub_menu_soy_estudiante_tramites = false;

        if(this.sub_menu_soy_docente == true){
          this.sub_menu_soy_docente = false;
        }else{
          this.sub_menu_soy_docente = true;

        }
      }


      
// Submenu 3

if(this.menu_encender == 'sub_menu_soy_estudiante_tramites'){
       
        if(this.sub_menu_soy_estudiante_tramites == true){
          this.sub_menu_soy_estudiante_tramites = false;
        }else{
          this.sub_menu_soy_estudiante_tramites = true;

        }
      }



// Submenu 4      

if(this.menu_encender == 'sub_menu_soy_estudiante_tramites_bajas'){
       
       if(this.sub_menu_soy_estudiante_tramites_bajas == true){
         this.sub_menu_soy_estudiante_tramites_bajas = false;
       }else{
         this.sub_menu_soy_estudiante_tramites_bajas = true;

       }
     }

      console.log(section)
      

      //console.log(`Redireccionar a: ${section}`);
    }
    
  }
};
</script>
