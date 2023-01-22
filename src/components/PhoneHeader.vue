<template>
  <div>
    <h1>Phone</h1>
    <p>{{this.number}} contacts with phone numbers</p>
  </div>
</template>

<script>
export default {
  name: 'PhoneHeader',
  props: ['number']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
    height: 150px;
    width: 500px;
    background-color: black;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-radius: 25px;
    
}

h1 {
    color: white;
    font-size: 3rem;
}

p {
  color: white;
}
</style>
