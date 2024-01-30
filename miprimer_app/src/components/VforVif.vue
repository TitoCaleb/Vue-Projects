<script setup>
const usuarios = [
  {
    id: 1,
    nombre: "Caleb",
    active: true,
  },
  {
    id: 2,
    nombre: "Charles",
    active: true,
  },
  {
    id: 3,
    nombre: "Carolina",
    active: false,
  },
  {
    id: 4,
    nombre: "Rebeca",
    active: true,
  },
  {
    id: 5,
    nombre: "Emilia",
    active: false,
  },
];
</script>

<template>
  <div>
    <ul>
      <template v-for="item of usuarios" :key="item.id">
        <li v-if="item.active">
          {{ item.nombre }}
        </li>
      </template>
    </ul>
  </div>
</template>

<style lang="scss" scoped></style>
