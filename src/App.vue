<script setup>
  import { ref } from 'vue';
 
  const name = ref("Srk");
  const tasks = ref(['Task One', 'Task Two', 'Task Three', 'Task Four', 'Task Five']);
  const newTask = ref('');

  const addTask = () => {
    if(newTask.value.trim() !== ''){
      tasks.value.push(newTask.value);
      newTask.value = '';
    }
  };
</script>

<template>
  <h1>Hello From {{name}}</h1>
  
  <div>
    <div>
      <form @submit.prevent="addTask">
        <label for="newTask"> Add Task</label></br>
        <input type="text" id="newTask" name="newTask" v-model="newTask">
        <button type="submit">Submit</button>
      </form>
      
    </div>
    <h3>Tasks</h3>
    <ol>
      <li v-for="task in tasks">{{ task }}</li>
    </ol>
  </div>
</template>

<style scoped></style>
