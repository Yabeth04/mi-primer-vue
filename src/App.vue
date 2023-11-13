<script setup>

const listFruts = ['😎', '😊', '🤣', '❤️', '😁'];
let seleccionMensaje = ''
const mensaje1 = 'Hola'
const mensaje2 = 'Buenos dias'
const mensaje3 = 'Buenas noches'
const mensaje4 = 'Me gusta VUE'

function funcionMensaje() {
  if (seleccionMensaje === '1') {
    alert(mensaje1)
  } else if (seleccionMensaje === '2') {
    alert(mensaje2)
  } else if (seleccionMensaje === '3') {
    alert(mensaje3)
  } else if (seleccionMensaje === '4') {
    alert(mensaje4)
  }
}



</script>

<template>
  <div>
    <ul>
      <li v-for="(frutas, index) in listFruts" :key="index">
        número: <span>{{ index }}{{ frutas }}</span>
      </li>
    </ul>

    <div class="seleccion">
      <label>Seleccione un mensaje a mostrar en pantalla</label>
      <select v-model="seleccionMensaje" @change="funcionMensaje">
        <option value="" disabled>Seleccione un mensaje</option>
        <option value='1'>{{ mensaje1 }}</option>
        <option value='2'>{{ mensaje2 }}</option>
        <option value="3">{{ mensaje3 }}</option>
        <option value="4">{{ mensaje4 }}</option>
      </select>
    </div>
  </div>
</template>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}



h1 {
  color: purple;
  text-transform: uppercase;
  font-weight: bold;
}

li {
  color: white;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  font-weight: bold;
  font-size: 30px;
  list-style: none;
  background-color: rgb(106, 106, 106);
  padding: 10px;
  margin: 5px;
}


.seleccion {
  background-color: rgb(48, 48, 48);
  height: 20vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: white;
  margin: 5px;
}

.seleccion label {
  font-size: 20px;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  font-weight: bold;
  padding: 10px;
}

.seleccion select {
  padding: 4px 20px;
  border-radius: 10px 10px 5px 5px;
}

.seleccion option {
  font-size: 13px;
}
</style>

