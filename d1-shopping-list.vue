<script setup>
  import {ref, reactive} from 'vue'
  const no = ref(0)
  const items = ref([
  ])
  const newItem = ref('')
  function addNewItem(){
    items.value.push({id: no.value++, item: newItem.value})
    newItem.value=''
  }
</script>
<template>
  <p>Press enter on your keyboard to add a new shopping item</p>
  <input v-model="newItem" @keyup.enter="addNewItem" placeholder="Add a new shopping item"></input>
  <ol>
    <li v-for="x in items" :key = "x.id">{{ x.item }}</li>
  </ol>
</template>

<style>

</style>
