<template>
  <div id="container">
      <h2>Did someone say Chuck Norris...</h2>
      <p v-on:quote="showQuote">{{message}} </p>
      <button v-on:click="generateQuote">Generate Quotes</button>
  </div>
</template>

<script>

export default {
  name: 'JokesContainer',
  props: {
    message: String
  },
  methods: {
      generateQuote() {
      this.$emit("generate-quote")
     },
     showQuote(){
       return response.value
     }
 }
}
</script>

<style>

#container {
  max-width: 1200px;
  height: auto;
  margin: 40px auto;
  border: 1px solid #000;
}

h2 {
    margin: 15px 0;
}

p {
    margin: 15px 0;
}

button {
    padding: 5px 15px;
    border-radius: 2px;
    border-color: #2c3e50;
    background: #2c3e50;
    color: #FFF;
    margin-bottom: 20px;
}

button:hover {
  opacity: .7;
}

</style>