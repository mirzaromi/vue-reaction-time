<script setup>
  import { reactive } from 'vue'
  const state = reactive({
    isPlaying: false,
    delay: null,
  })
  function start() {
    state.isPlaying = true
    state.delay = 2000 + Math.random()*5000
    console.log(state.delay)
  }
</script>

<template>
  <h1>Mirza Reaction Timer</h1>
  <button @click="start">play</button>
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
