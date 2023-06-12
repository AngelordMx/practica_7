<script setup>
import {ref} from 'vue'
const name = 'vue dinamico';

//netidi - methods
const Arraynumeros=ref([]);
const counter = ref (0)
const incremento = () => {
  console.log('aumentar contador')
  counter.value++;
  console.log(counter);
}

const reduccion = () => {
  console.log('reducir contador')
  counter.value--;
  console.log(counter);
}

const reseteo = () => {
  console.log('resetear contador')
  counter.value = 0;
  console.log(counter);
}

const numfav = () => {
  Arraynumeros.value.push(counter.value);

}
</script>

<template>
  <h1>Hola {{ name.toUpperCas }}</h1>
  <h2 v-if="counter < 0">
    <p style="color: red">{{ counter }}</p>
  </h2>
  <h2 v-if="counter > 0">
    <p style="color: green">{{ counter }}</p>
  </h2>
  <h2 v-if="counter == 0">
    <p style="color: gray">{{ counter }}</p>
  </h2>
  <button @click="incremento">Aumentar</button>
  <button @click="reduccion">Reducir</button>
  <button @click="reseteo">Resetear</button>
  
  <button @click="numfav"> Add</button>
  <ul>
    <li
    v-for="{numero, index} in Arraynumeros"
    :key="numero"
    >{{ index }} - {{ numero  }}
    </li>
  </ul>

  

</template>

<style>
h1 {
  color: red
}
</style>