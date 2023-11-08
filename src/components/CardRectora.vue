<template>
  <div class="container">
    <div class="message-container">
      <div class="message-text">
        <br>
        <br>
        <br>
        <p class="text-h4 font-weight-bold" style="font-family: 'Roboto', sans-serif; color: black;">Mensaje de <span style="color:#00B394;">Nuestra Rectora</span></p>
        <p style="text-align: justify; font-family: 'Roboto', sans-serif; font-weight: 600; font-size: 16px;">
          Es un gusto muy especial dirigirme a todas y todos los integrantes de la Comunidad UTL: estudiantado, personal docente y administrativo, y demás plantilla actoral de nuestro entorno universitario.
          
          Desde marzo ya estamos de regreso a casa. Y en este deseo de normalizar nuestra vida universitaria, hemos vivenciado un proceso necesario de reencuentro, de reconocimiento, para compensar esos meses de confinamiento que afectaron nuestra forma de relacionarnos personal y colectivamente. Pero si algo nos define, es que somos una institución tecnológicamente humana, en innovación y adaptación constante.
          
          Y en esta nueva realidad, nos enfocamos en dar prioridad a la salud, atendiendo en todo momento a las medidas sanitarias para mantener a raya todo contagio. Además, es necesario, como dice nuestro Gobernador Diego Sinhué Rodríguez, reinventarnos para ser mejores, esto es, crear nuevas formas de realizar el proceso formativo, académico, administrativo para que nuestra UTL siga siendo considerada un bastión importante del ecosistema educativo guanajuatense.
          
          Como bien lo dice nuestro lema “Somos Leones, Somos Leonas”, les invito a construir entre todos una “guarida segura” donde prevalezca un ambiente de colaboración y convivencia, donde nos sintamos a gusto en “nuestra guarida”, promoviendo una cultura de paz y de respeto a nuestros derechos humanos fundamentales. Acorde a los nuevos tiempos, mostremos a la sociedad que la UTL es íntegra, inclusiva y sostenible.
        </p>
      </div>
      <div class="rectora-info">
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <img src="@/assets/rectora.png" alt="Yoloxóchitl Bustamante Díez" style="width: 80%">
        <h1 class="rectora-name">Yoloxóchitl Bustamante Díez</h1>
        <p class="rectora-role">Encargada de despacho de Rectoría</p>
      </div>
    </div>
    <hr class="horizontal-line">
    <div class="text-noticias">
      <br>
      <a href="" style="text-decoration: none; color: black">Noticias ></a>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-left: 12%;
}

.message-container {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.message-text {
  flex: 1;
}

.rectora-info {
  text-align: center;
}
.horizontal-line {
  width: 100%;
  border-top: -9px solid #000000; /* Color de la línea horizontal */
  margin-top: 50px; /* Ajusta el margen superior de la línea horizontal según sea necesario */
}

.text-noticias {
  color: rgb(0, 0, 0);
  font-family: 'Roboto Flex', sans-serif;
  font-size: 44px; /* Tamaño del texto de noticias */
  margin-left: 3px; /* Ajusta el margen izquierdo del texto de noticias según sea necesario */
  margin-top:-50px; /* Ajusta el margen superior del texto de noticias según sea necesario */
}
.rectora-info {
  text-align: center;
}

.rectora-name {
  margin-left: 50px; /* Ajusta el margen izquierdo del nombre de la rectora según sea necesario */
}

.rectora-role {
  margin-left: 200px; /* Ajusta el margen izquierdo del cargo de la rectora según sea necesario */
}

.message-text {
  flex: 1;
}
</style>