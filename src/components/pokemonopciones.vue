<template>
  <div class="opciones-container">
    <ul>
      <li>Charmander</li>
      <li>Pidgeot</li>
      <li>Bulbasaur</li>
      <li>Caterpie</li>
    </ul>
  </div>
</template>

<script>
export default {};
</script>

<style>
ul {
  list-style-type: none;
}
li{
    background-color: white;
    border-radius: 5px;
    border: 1px solid;
    cursor: pointer;
    width: 250px;
    margin-top: 10px;
    /* padding: 10px;
    margin: 10px; */
}
.opciones-container{
    display: flex;
    justify-content: center;
}

</style>