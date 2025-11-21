<script>
  export default{
    data () {
      return {
        name: "Srk",
        status: 'active',
        numArray:  ['One', 'Two', 'Three', 'Four', 'Five'],
        link: "https://vuejs.org",
      }
    },
    methods: {
      toggleSttaus (){
        if(this.status == "active"){
          this.status = "inactive";
        }else{
          this.status = "active";
        }
      }
    },
  };
</script>

<template>
  <h1>Hello From {{name}}</h1>
  <p>Status is {{status}}</p>
  <button v-on:click="toggleSttaus" >Toggle Status</button>
  <div>
    <h3>Array Loop</h3>
    <ol>
      <li v-for="number in numArray">{{ number }}</li>
    </ol>
  </div>
  <a :href="link" target="_blank">Go to Vue Official Page</a>
</template>

<style scoped></style>
