<script setup>
  import { reactive } from 'vue'
  import Block from './components/Block.vue'
  const state = reactive({
    isPlaying: false,
    delay: null,
    score: null,
    showResult: false,
  })
  function start() {
    state.isPlaying = true
    state.delay = 2000 + Math.random()*5000
    state.showResult = false
    console.log(state.delay)
  }
  function endGame(reactionTime) {
    state.score = reactionTime
    state.isPlaying = false
    state.showResult = true
  }
</script>

<template>
  <h1>Mirza Reaction Timer</h1>
  <button @click="start" :disabled="state.isPlaying">play</button>
  <p v-if="state.showResult">reaction time = {{state.score}} ms</p>
  <Block v-if="state.isPlaying" :delay="state.delay" @end="endGame"/>
</template>

<style>
@import './assets/base.css';

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
  color: #38eba6;
  font-weight: normal;
}

</style>
