<script>
  export default{
    data () {
      return {
        name: "Srk",
        status: 'active',
        numArray:  ['One', 'Two', 'Three', 'Four', 'Five'],
      }
    },
  };
</script>

<template>
  <h1>Hello From {{name}}</h1>
  <p v-if="status == 'active' ">This is True</p>
  <p v-else="status">Status is False</p>

  <div>
    <h3>Array Loop</h3>
    <ol>
      <li v-for="number in numArray">{{ number }}</li>
    </ol>
  </div>
</template>

<style scoped></style>
