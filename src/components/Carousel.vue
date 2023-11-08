<template>
  <div class="timelapse-container" style="margin-top: -100px; z-index: 1; box-shadow: 0px 50px 50px rgba(0, 0, 0, 0.5);">
    <video id="timelapseVideo" autoplay muted loop>
      <source src="@/assets/IMG_1394.mp4" type="video/mp4">
      Tu navegador no soporta el elemento de video.
    </video>
  </div>
</template>

<script>
import MenuSuperior from '../components/MenuSuperior.vue';

export default {
  components: {
    MenuSuperior
  },
  mounted() {
    // Ajusta el tamaño del video para cubrir toda la pantalla sin espacios en blanco
    const video = document.getElementById('timelapseVideo');
    const toolbarHeight = document.querySelector('.MenuSuperior').offsetHeight;
    const windowHeight = window.innerHeight - toolbarHeight;
    const windowWidth = window.innerWidth;
    const videoAspectRatio = video.videoWidth / video.videoHeight;
    const windowAspectRatio = windowWidth / windowHeight;

    if (windowAspectRatio > videoAspectRatio) {
      // La ventana es más ancha que el video, ajusta el ancho del video
      video.style.width = '100%';
      video.style.height = 'auto';
    } else {
      // La ventana es más alta que el video, ajusta la altura del video
      video.style.width = 'auto';
      video.style.height = '100%';
    }

    // Ajusta la posición del video para que cubra el toolbar
    video.style.marginTop = -toolbarHeight + 'px';
  }
};
</script>

<style scoped>
.timelapse-container {
  position: relative;
  width: 100%;
  height: 100vh; /* Asegura que el contenedor del video ocupe toda la altura de la pantalla */
  overflow: hidden; /* Oculta cualquier desbordamiento del video */
}

#timelapseVideo {
  object-fit: cover; /* Asegura que el video cubra completamente el contenedor sin distorsionarse */
  width: 100%; /* Asegura que el video ocupe todo el espacio disponible dentro del contenedor */
  height: 100%; /* Asegura que el video ocupe todo el espacio disponible dentro del contenedor */
}
</style>
