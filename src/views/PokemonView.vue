<template>
  <Pokemonimagen :pokemonId="pokemonGanador" />
  <Pokemonopciones
    @selecionado="evaluarGanador($event)"
    :listaPokemon="pokemonArr"
  />

  <div v-if="estado" class="mensaje">
    <h1>Ganador</h1>
  </div>
</template>

<script>
import Pokemonimagen from "@/components/pokemonimagen.vue";
import Pokemonopciones from "@/components/pokemonopciones.vue";
import {
  obtenerVectorPokemonFachada,
  obtenerAleatorioFachada,
} from "../clients/PokemonClient.js";

export default {
  components: {
    Pokemonimagen,
    Pokemonopciones,
  },
  data() {
    return {
      pokemonArr: [],
      pokemonGanador: null,
      estado: false,
    };
  },
  mounted() {
    this.iniciarJuego();
  },
  methods: {
    async iniciarJuego() {
      console.log("Componente Montado");
      this.pokemonArr = await obtenerVectorPokemonFachada();

      const idaleatoreo = obtenerAleatorioFachada(0, 3);
      this.pokemonGanador = this.pokemonArr[idaleatoreo].id;
    },
    evaluarGanador(idGanador) {
      console.log("Valor recibido desde padre: \n" + idGanador);
      if (idGanador == this.pokemonGanador) {
        console.log("ganador");
        this.estado = true;
      } else {
        console.log("perdedor");
      }
    },
  },
};
</script>

<style>
.mensaje {
  position: relative;
  height: 200px;
  left: 45%;
}
</style>