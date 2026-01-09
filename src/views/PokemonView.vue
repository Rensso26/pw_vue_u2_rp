<template>
  <Pokemonimagen v-if="mostrar" :pokemonId="pokemonGanador" />
  <Pokemonopciones
    @selecionado="evaluarGanador($event)"
    :listaPokemon="pokemonArr"
  />
  <button @click="destruir()">Destruir</button>

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
      mostrar: true,
    };
  },
  beforeCreate() {
    console.log("En beforeCreate: apenas inicia la instancia del componente");
  },
  created() {
    console.log("En created: ya se resolvieron data, computed, methods, watch");
  },

  /*Montage : renderiza o visualiza el componente*/
  beforeMount() {
    console.log(
      "En beforeMount: justo antes del primer render de un elemento HTML"
    );
  },
  mounted() {
    console.log("En mounted: el componente ya se renderizó");
  },
  mounted() {
    this.iniciarJuego();
  },
  /*Actualización de un componente*/
  beforeUpdate() {
    console.log(
      "beforeUpdate: cuando cambió data/props y Vue está por re-renderizar"
    );
  },
  updated() {
    console.log("updated: Cuando ya se actualizó tras la re-renderización");
  },
  /*Desmontaje de un componente*/
  beforeUnmount() {
    console.log("beforeUnmount: justo antes de que el componente se destruya.");
  },
  unmounted() {
    console.log("unmounted: ya fue removido del DOM y destruido.");
  },
  methods: {
    destruir() {
      this.mostrar = false;
    },
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