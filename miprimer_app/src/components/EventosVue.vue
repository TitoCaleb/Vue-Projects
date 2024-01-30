<template>
  <div>
    <p :class="classCounter">{{ counter }}</p>
    <button @click="increment">Aumentar 5</button>
    <button @click="counter++">Aumentar 1</button>
    <button @click="counter--">Restar 1</button>
    <button @click="decrement">Restar 5</button>
    <button @click="resetear">Resetear</button>
    <button @click="addFavorite" :disabled="classDisabled">Agregar a favoritos</button>
    <ul>
      <template v-for="item in listFavorites" :key="item">
        <li>{{ item }}</li>
      </template>
    </ul>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue';

  const counter = ref(0)
  const listFavorites = ref([])

  const decrement = () => {
    counter.value -= 5
  }
  const increment = () => {
    counter.value += 5
  }

  const resetear = () => {
    counter.value = 0
  }

  const classCounter = computed(() => {
    if (counter.value === 0){
      return 'zero'
    }

    if (counter.value < 0) {
      return 'negative'
    } else {
      return 'positive'
    }
  })

  const addFavorite = () => {
    listFavorites.value.push(counter.value)
  }

  const classDisabled = computed(() => {
    let index = listFavorites.value.findIndex(item => item === counter.value)
    if(index === -1){
      return false
    }
    return true
  })
  
</script>

<style scoped>
  .positive{
    color: green;
  }

  .negative {
    color: red;
  }
</style>