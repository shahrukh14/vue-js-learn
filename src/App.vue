<script>
import { ref } from 'vue';

  export default{
    setup () {
      const name = ref("Srk");
      const status = ref("active");
      const numArray = ref(['One', 'Two', 'Three', 'Four', 'Five']);

      const toggleSttaus = () => {
        if(status.value == "active"){
          status.value = "inactive";
        }else{
          status.value = "active";
        }
      };

      return {
        name,
        status,
        numArray,
        toggleSttaus,
      }
    },
  };
</script>

<template>
  <h1>Hello From {{name}}</h1>
  <p>Status is {{status}}</p>
  <button @click="toggleSttaus" >Toggle Status</button>
  <div>
    <h3>Array Loop</h3>
    <ol>
      <li v-for="number in numArray">{{ number }}</li>
    </ol>
  </div>
</template>

<style scoped></style>
