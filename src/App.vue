<script setup>
  import { onMounted, ref } from 'vue';
 
  const name = ref("Srk");
  const tasks = ref(['Task One', 'Task Two', 'Task Three', 'Task Four', 'Task Five']);
  const newTask = ref('');

  const addTask = () => {
    if(newTask.value.trim() !== ''){
      tasks.value.push(newTask.value);
      newTask.value = '';
    }
  };

  const deleteTask = (index) => {
    tasks.value.splice(index, 1);
  };

  onMounted(async () => {
    try{
      const response = await fetch('https://jsonplaceholder.typicode.com/todos');
      const data = await response.json();
      tasks.value = data.map((task) => task.title);
    }catch (error) {
      console.log('Error : ' + error)
    }
  });
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
      <li v-for="(task, index) in tasks" :key ="task">
        <span>{{ task }}</span>
        <button @click="deleteTask(index)">x</button>
      </li>
    </ol>
  </div>
</template>

<style scoped></style>
