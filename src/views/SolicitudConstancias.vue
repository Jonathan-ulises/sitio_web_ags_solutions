<template>
    <div>
        <div>
            <v-img src="../assets/fondos/fondo_constancias.png"
            style="margin-top: -100px; z-index: 1; box-shadow: 0px 50px 50px rgba(0, 0, 0, 0.5);"
            max-height
            with
            cover
            aspect-ratio="16/9">
      <p class="text-h1 text-start font-weight-class text-right"
       style="color:#00B394; font-family: 'Roboto Flex', sans-serif;font-weight: bold; margin-top: 250px; margin-left: 1%;">
      Solicitud de Constancias
    </p>
    <p class="text-justify" style="color:white; font-family: 'Roboto Flex', sans-serif; font-size: 17px; margin: 0 20px;">
        Se emite con los datos de la persona de la institución que valida la información, así como un código de identificación en el documento para cualquier cotejo o validación posterior, en caso de ser requerido por quien recibe el documento.
    </p>
    <p class="text-justify" style="color:white; font-family: 'Roboto Flex', sans-serif; font-size: 17px; margin: 0 20px;">
        En caso de requerir una constancia de estudios, bajo las especificaciones expuestas, deberás de realizar el siguiente proceso: 
    </p>
    <br>
    <br>
            </v-img>
        </div>
            <div>
                <v-col>
                    <div style="width: 100%;"><div style="position: relative; padding-bottom: 56.25%; padding-top: 0; height: 0;"><iframe title="CONSTANCIA 21-03-2023" frameborder="0" width="1200px" height="675px" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;" src="https://view.genial.ly/62461312c1dd840018544a09" type="text/html" allowscriptaccess="always" allowfullscreen="true" scrolling="yes" allownetworking="all"></iframe> </div> </div>
                </v-col>
            </div>
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
