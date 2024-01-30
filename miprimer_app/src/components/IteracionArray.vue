<script setup>
const arrayFrutas = ["manzana", "platano", "sandia", "fresa", "cerezas"];
const usuarios = [
  {
    id: 1,
    nombre: "Caleb",
  },
  {
    id: 2,
    nombre: "Charles",
    apodo: "Papá",
  },
  {
    id: 3,
    nombre: "Carolina",
    apodo: "Mamá",
  },
  {
    id: 4,
    nombre: "Rebeca",
  },
  {
    id: 5,
    nombre: "Emilia",
    apodo: "Emis",
  },
];
</script>

<template>
  <ul>
    <li v-for="usuario in usuarios" :key="usuario.id">
      {{ usuario.nombre }} AKA: {{ usuario.apodo }}
    </li>
  </ul>
</template>

<style scoped></style>
