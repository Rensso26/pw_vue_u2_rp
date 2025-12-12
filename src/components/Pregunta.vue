<template>
  <div class="container">
    <img v-if="imagen" :src="imagen" alt="No se puede mostrar" />
    
    <div class="obscuro"></div>
    <div class="pregunta-container">
      <input v-model="pregunta" type="text" placeholder="Hazme una pregunta" />
      <p>Recuerda terminar con el signo de interrogaci&oacute;n (&quest;)</p>

      <h2>{{ pregunta }}</h2>
      <h1>{{ respuesta }}</h1>
    </div>
  </div>
</template>

<script>
import { consumirAPIfachada } from "../clients/YesNoClient.js";
export default {
  data() {
    return {
      pregunta: null,
      respuesta: null,
      imagen: null,
    };
  },
  methods: {
    async consumirAPIfachada() {
      return await consumirAPIfachada();
    },

    async consumir() {
      const resp = await this.consumirAPIfachada();
      this.imagen = resp.image;
      console.log("Respuesta final");
      console.log(resp);
      console.log(resp.answer);
      this.respuesta = resp.answer;
    },
  },
  watch: {
    pregunta(value, oldValue) {
      console.log(value);
      console.log(oldValue);
      if (value.endsWith("?")) {
        this.respuesta = "Pensando...";
        this.consumir();
      }
    },
  },
};
</script>

<style>
img, .obscuro {
  height: 100vh;
  width: 100vw;
  max-height: 100%;
  max-width: 100%;
  position: fixed;
  left: 0px;
  top: 0px;
}

input {
  width: 250px;
  padding: 10px 15px;
  border-radius: 5px;
  border: none;
}
input:focus {
  outline: none;
}
.container,
.pregunta-container {
  display: flex;
  justify-content: center;
  align-items: center;
  /* flex-direction: column; */
}
.pregunta-container {
  padding: 200px;
  z-index: 100;
  min-height: 100hv;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  color: white;
  font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
h1 {
  font-size: 100px;
}
p {
  font-size: 20px;
}
h2 {
  margin-top: 150px;
}

.obscuro {
  background-color: rgba(0, 0, 0, 0.4);
}
</style>