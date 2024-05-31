<template>
  <h1>Reaction Timer </h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Result :showResults="showResults" :score="score"></Result>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Results.vue'
export default {
  name: 'App',
  components: {
    Block,
    Result
  },
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  padding: 10px 24px;
  border: none;
  outline: none;
  color:#fff;
  background: rgb(107, 107, 240);
  border-radius: 5px;
}

</style>
