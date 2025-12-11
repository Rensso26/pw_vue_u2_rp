<template>
  <!-- <div><ContadorView /></div> -->
  <!-- <div><DirectivasView /></div> -->
  <div><PreguntaView /></div>
</template>

<script>
import ContadorView from "./views/ContadorView.vue";
import DirectivasView from "./views/DirectivasView.vue";
import PreguntaView from "./views/PreguntaView.vue";
export default {
  components: {
    ContadorView,
    DirectivasView,
    PreguntaView
  },
};
</script>

<style>
</style>