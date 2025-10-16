<script setup>
  import {ref, reactive} from 'vue'
  const name = ref('Name')
</script>
<template>
  <input v-model="name"></input>
  <h1>Hello, {{ name }}</h1>
</template>

<style>

</style>
