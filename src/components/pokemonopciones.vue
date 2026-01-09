<template>
  <div class="opciones-container">
    <ul>
      <li
        v-on:click="pasarPadre(pokemon.id)"
        v-for="pokemon in listaPokemon"
        :key="pokemon.id"
      >
        {{ pokemon.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    listaPokemon: {
      type: Array,
      required: true,
    },
  },
  methods: {
    pasarPadre(id) {
      this.$emit("selecionado", id);
    },
  },
};
</script>

<style>
ul {
  list-style-type: none;
}
li {
  background-color: white;
  border-radius: 5px;
  border: 1px solid;
  cursor: pointer;
  width: 250px;
  margin-top: 10px;
  /* padding: 10px;
    margin: 10px; */
}
.opciones-container {
  display: flex;
  justify-content: center;
}
</style>