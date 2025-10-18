<script setup>
  import { ref, reactive, computed } from 'vue'

  let id = 0
  const taskList = ref([
    {id: id++, name: 'Complete 10 pushups',checked: false, categories: ['sports']}
  ])

  const newTask=ref('')

  const hiddenCompletedTasks = computed(() => {
    return taskList.value.filter(task => task.checked == false)
  })
  const hidden = ref(false)

  function remove(taskId){
    taskList.value = taskList.value.filter(task => task.id != taskId)
  }

  function add(){
    taskList.value.push({id: id++, name: newTask.value, checked: false, categories: [tag.value]})
    newTask.value = ''
    tag.value = ''
  }

  const categories = ref(['studying','sports','music','groceries'])
  const tag = ref('')

</script>

<template>
  <form @submit.prevent="add">
    <input v-model="newTask" placeholder="Add a new task"></input>
    <label>Select a category</label>
    <select v-model="tag">
      <option v-for="category in categories">{{ category }}</option>
    </select>
    <button type="submit">Add</button>
  </form>
  <ul>
    <li v-for="task in (hidden ? hiddenCompletedTasks : taskList)" :class="{'checked': task.checked}">
      <input type="checkbox" v-model="task.checked"></input>
      <span>{{ task.name }} {{ task.categories }}</span>
      <button @click="remove(task.id)">x</button>
    </li>
  </ul>
  <button @click="hidden = !hidden">{{ hidden ? 'Show all tasks' : 'Hide all completed tasks'}}</button>
</template>

<style>
.checked{
  text-decoration: line-through;
  color: gray
}
</style>
