<script setup>
  const objetoFruta = {
    name: 'Platano',
    price: '$ 10.0',
    descripcion: 'Color amarillo de buen sabor',
    id: 1
  }
</script>

<template>
  <div>
    <ul>
      <li v-for="(value, property, index) in objetoFruta" :key="index">
        {{ property }}: {{ value }} 
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>

</style>