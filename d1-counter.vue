<script setup>
  import {ref} from 'vue'
  const counter = ref(0)
  function increment(){
    counter.value++
  }
  function decrement(){
    counter.value--
  }
</script>
<template>
  <h1 style="text-align:center">Counter App</h1>
  <p style="text-align:center">{{ counter }}</p>
  <div style="text-align:center">
    <button class="btn" v-on:click="increment">+1</button>
    <button class="btn" v-on:click="decrement">-1</button>
  </div>
  
</template>

<style>
.btn{
  margin: 10px;
  padding: 4px 15px 4px 15px
}
</style>
