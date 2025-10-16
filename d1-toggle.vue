<script setup>
  import {ref, reactive} from 'vue'
  const isShown = ref(true)
  const btnText = ref('Hide the paragraph')
  function toggle(){
    isShown.value = !isShown.value
    btnText.value = isShown.value ? 'Hide the paragraph' : 'Show the paragraph'
  }
</script>
<template>
  <p v-if="isShown">Hello</p>
  <button v-on:click="toggle">{{ btnText }}</button>
</template>

<style>

</style>
