<template>
  <div id="app">
    <Header />
    <Jokes-Container v-on:generate-quote="getQuote()" :message=msg />
    
  </div>
</template>

<script>
import Header from './components/Header.vue'
import JokesContainer from './components/JokesContainer.vue'


export default {
  name: 'app',
  components: {
    Header,
    JokesContainer
  },
  data() {
    return {
      msg: ''
    }
  },
  methods: {
    getQuote(){
      let self = this
      fetch('https://api.chucknorris.io/jokes/random')
      .then(function(response) {
        return response.json();
      })
      .then(function(response) {
        console.log(response);
        console.log(response.value);

        return self.msg = response.value
      });
    }
  },
  mounted: function(){
    
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f15b23;
}
</style>
