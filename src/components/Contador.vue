<template>
  <div>
    <h1>{{ tit }}</h1>
    <p>{{ numero }} <sup>2</sup>= {{ obtenerCuadrado() }}</p>
    <p>{{ numero }} <sup>2</sup>= {{ obtenerCuadrado() }}</p>
    <p>{{ numero }} <sup>2</sup>= {{ calcularCuadrado }}</p>
    <p>{{ numero }} <sup>2</sup>= {{ calcularCuadrado }}</p>
    <p>{{ numero }} <sup>3</sup>= {{ obtenerCubo() }}</p>
    <p>{{ numero }} <sup>3</sup>= {{ obtenerCubo() }}</p>
    <p>{{ numero }} <sup>3</sup>= {{ calcularCubo }}</p>
    <p>{{ numero }} <sup>3</sup>= {{ calcularCubo }}</p>

    <div>
      <button @:click="incrementar()">+1</button>
      <button @:click="decrementar()">-1</button>
      <p v-show="this.mostrar">prueba</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero: this.inicio,
      numero2: 20,
      titulo: "Contador",
    };
  },
  methods: {
    obtenerCuadrado() {
      console.log("Entro a obtener cuadrado");
      return this.numero * this.numero;
    },
    obtenerCubo() {
      return this.numero * this.numero * this.numero;
    },
    incrementar() {
      console.log(this.tit);
      this.numero++;
    },
    decrementar() {
      this.numero--;
    },
  },
  computed: {
    calcularCuadrado() {
      console.log("Entro a propiedad computed");
      return this.numero * this.numero;
    },
    calcularCubo() {
      return this.numero * this.numero * this.numero;
    },
  },
  // props: ["tit", "inicio", "mostrar"],
  props: {
    tit: String,
    inicio: {
      type: Number,
      default: 99,
      validator(value) {
        return value > 10;
      },
    },
    mostrar: Boolean,
  },
  /*String, Numbre, Boolean, Array, Object, Date, Function, BigInt*/
};
</script>

<style>
</style>