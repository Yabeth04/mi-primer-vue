<script setup>
import { ref } from 'vue';

const contador = ref(0)

const reset = () =>{
  contador.value = 0
}

const incrementa = () =>{
  contador.value++;
}
const disminuye = () =>{
  contador.value--;
}







</script>

<template>
<h2 :class="contador > 0 ? 'positive' : 'negative' " > {{ contador }} </h2>
<br>
<button @click="incrementa">aumenta</button>
<button @click="disminuye">disminuye</button>
<button @click="reset">reset</button>


</template>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.positive{
  color: green;
}

.negative{
  color: red;
}


</style>


