<template>
  <div class="container">
    <img
      src="https://yesno.wtf/assets/yes/5-64c2804cc48057b94fd0b3eaf323d92c.gif"
      alt="No se puede mostrar"
    />
    <div class="pregunta-container">
      <input type="text" placeholder="Hazme una pregunta" />
      <p>Recuerda terminar con el signo de interrogaci&oacute;n (&quest;)</p>

      <h2>Sere millonario&quest;</h2>
      <h1>Yes, No</h1>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
img {
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
input:focus{
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
p{
  font-size: 20px;
}
h2{
  margin-top: 150px;
}
</style>