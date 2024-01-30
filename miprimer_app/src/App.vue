<script setup>
import EventosVue from "./components/EventosVue.vue";
import IteracionArray from "./components/IteracionArray.vue";
import IteracionObjeto from "./components/IteracionObjeto.vue";
import VforVif from "./components/VforVif.vue";

let name = "Aprendiendo VueJS";
let styleColor = "color: skyblue";
let isTrue = true;
let colores = ["red", "blue", "orange"];
</script>

<template>
  <h1 class="titulo">{{ name.toUpperCase() }}</h1>
  <h2 :style="styleColor">soy color azul</h2>
  <h3 style="color: green">
    {{ isTrue ? "Es todo verdad" : "Es todo mentira" }}
  </h3>
  <h4 :style="`color: ${colores[2]}`">soy {{ colores[2] }}</h4>
  <p v-if="!isTrue">Estoy inactivo</p>
  <p v-else>Estoy activo</p>

  <h1>Iteracion array</h1>
  <IteracionArray />

  <h1>Iteracion objeto</h1>
  <IteracionObjeto />

  <h1>Iteracion condicional</h1>
  <VforVif />

  <h1>Eventos en VUEjs</h1>
  <EventosVue />
</template>

<style scoped>
.titulo {
  color: red;
}
</style>
