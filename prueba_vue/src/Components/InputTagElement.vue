<script setup>
  import { ref } from 'vue';

  const currentValue = ref('')
  const status = ref('')
  const tags = ref([])

  const handleKeyDown = ({key}) => {
    if(key === 'Backspace' && currentValue.value === '') {
      tags.value.pop()
    }
  }

  const handleSubmit = () => {
    if(currentValue.value === '') {
      status.value = 'error'
      return
    }
    status.value = ''

    tags.value.push({
      id: crypto.randomUUID(),
      name: currentValue.value
    })
    currentValue.value = ''
  }

  const deleteTag = tagId => {
    const prev = [...tags.value]
    let filtrados = prev.filter(tag => tag.id !== tagId)
    tags.value = filtrados
  }

</script>

<template>
  <div class="inputTag">
    <div class="tags">
      <div class="tag" v-for="(tag, index) in tags" :key='index'>
        {{ tag.name }} <button @click="deleteTag(tag.id)">X</button>
      </div>
    </div>
    <form @submit.prevent="handleSubmit">
      <input v-model="currentValue" type="text" @keydown="handleKeyDown"/>
    </form>
  </div>
</template>

<style  scoped>

  .tags{
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

</style>