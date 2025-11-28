<template>
  <div>
    <label for="id_nombre">Nombre</label>
    <input v-model="nombre" id="id_nombre" type="text" />
    <label for="id_apellido">Apellido</label>
    <input v-model="apellido" id="id_apellido" type="text" />
    <p>{{ nombre }}</p>
    <p>{{ apellido }}</p>
    <button v-on:click="imprimirNombre()">Imprimir Nombre</button>
    <button v-on:click="agregarEstudiante()">Agregar Estudiante</button>

    <h1>{{ arreglo[0] }}</h1>
    <ul>
      <li v-show="nombre" v-for="{ nombre, apellido } in arreglo" :key="nombre">
        {{ nombre }} - {{ apellido }}
      </li>
    </ul>
    <h2>Tabla</h2>
    <div>
      <table>
        <thead>
          <th>Nombre</th>
          <th>Apellido</th>
        </thead>
        <tbody v-for="{ nombre, apellido } in arreglo" :key="nombre">
          <td>{{ nombre }}</td>
          <td>{{ apellido }}</td>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nombre: null,
      apellido: null,
      arreglo: [],
    };
  },
  methods: {
    imprimirNombre() {
      console.log(this.nombre);
    },
    agregarEstudiante() {
      const estu = {
        nombre: this.nombre,
        apellido: this.apellido,
      };

      console.log("Se agrega Estudiante");
      console.log(estu);

      this.arreglo.push(estu);
      this.limpiarFormulario();
    },
    limpiarFormulario() {
      this.nombre = "";
      this.apellido = "";
    },
  },
};
</script>

<style>
table,td,th{
  border: 1px solid black;
  border-collapse: collapse;
  padding: 8px;
  margin: 22px;
}
</style>