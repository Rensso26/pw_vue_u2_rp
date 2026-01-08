<template>
  <!-- <div><ContadorView /></div> -->
  <!-- <div><DirectivasView /></div> -->
  <!-- <div><PreguntaView /></div> -->
   <div><PokemonView /></div>
</template>

<script>
import ContadorView from "./views/ContadorView.vue";
import DirectivasView from "./views/DirectivasView.vue";
import PokemonView from "./views/PokemonView.vue";
import PreguntaView from "./views/PreguntaView.vue";
export default {
  components: {
    ContadorView,
    DirectivasView,
    PreguntaView,
    PokemonView,
  },
};
</script>

<style>
</style>