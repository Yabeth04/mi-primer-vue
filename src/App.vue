<template>
  <div class="main">
    <h1>¡Hola a <span>todos</span>!</h1>
    <p>Ingresa un mensaje a guardar</p>
    <div class="box_guardar">
      <input type="text" class="barra" v-model="mensajeGuardar" >
      <a @click="funcionGuardarMensaje()">Guardar</a>

    </div>
    <p class="par_indicator">AQUI SE MOSTRARAN TODOS TUS MENSAJES</p>
    <ul>
      <li v-for="mensaje in lista" :key="index">{{ mensaje }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lista: []
    }
  },
  methods: {
    funcionGuardarMensaje() {
      if (this.mensajeGuardar === '') {
        alert('No se permiten guardar mensajes vacíos');
      } else {
        this.lista.push(this.mensajeGuardar); //.push(enviar o empujar a algo. Empujar hacia un objeto para depositarlo ahi)
        this.mensajeGuardar = ''; //resetea el input
      }
    }

  },
}
</script>

<style scoped>
* {
  padding: 0;
  list-style: none;
  font-family: 'Cascadia Code';
  margin: 0;
  box-sizing: border-box;
}

h1{
  color: rgb(73, 73, 73);
}
.main {
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
  height: 80vh;
  width: 180vh;
}

input{
  margin: 20px;
  padding: 2px;
  border-radius: 5px;
  background-color: rgb(231, 231, 231);
  border: red solid 0px;
  text-align: center;
  align-items: center;
}



ul {
  color: white;
  background-color: rgb(119, 214, 119);
  width: 250px;
  max-height: 200px; /* Cambiado de 'height' a 'max-height' */
  text-align: center;
  align-items: center;
  justify-content: center;
  border: 3px solid rgb(43, 152, 43);
  border-radius: 6px;
  overflow-y: auto; /* Agregado para habilitar la barra de desplazamiento vertical si es necesario */
}
.par_indicator{
  font-size: 13px;
  font-weight: bold;
  color: rgb(126, 126, 126);
  margin-bottom: 8px;
}

span{
  color: rgb(43, 152, 43);
}

a{
  align-items: center;
  border: 2px solid green;
  border-radius: 12px;
  padding: 2px 12px;
  color: rgba(43,152,43);
  font-weight: bold;
}

a:hover {
  color: white;
  background-color: rgb(97, 190, 97);
  border: 2px solid white;
  cursor: pointer;
}

@media (max-width:1020px){
  .main {
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
  height: 70vh;
  width: 150vh;
}

@media (max-width:880px){
  .main {
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
  height: 70vh;
  width: 130vh;
}
}

@media (max-width:800px){
  .main {
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
  height: 80vh;
  width: 110vh;
}
}
@media (max-width:700px){
  .main {
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
  height: 90vh;
  width: 100vh;
}
}

@media (max-width:535px){
  .main {
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
  height: 80vh;
  width: 75vh;
}
}

@media (max-width:400px){
  .main {
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
  height: 70vh;
  width: 50vh;
}
.box_guardar{
  display: flex;
  align-items: center;
}
}
}
</style>