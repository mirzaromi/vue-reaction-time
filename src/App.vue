<script setup>
  import { reactive } from 'vue'
  import Block from './components/Block.vue'
  import Result from './components/Result.vue'
  import Form from './components/Form.vue'


  const state = reactive({
    isPlaying: false,
    delay: null,
    score: null,
    showResult: false,
    formShow: true,
    usarname: null,
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

  function afterForm(nama) {
    state.formShow = !state.formShow
    state.usarname = nama
  }

  function reset() {
    state.formShow = !state.formShow
    state.usarname = null
    state.isPlaying = false
    state.showResult = false
    state.score = null
    state.delay = null
  }
</script>

<template>
  <Form v-if="state.formShow" @next="afterForm" />
  <h1>{{ state.usarname }} Reaction Timer</h1>
  <button class="reset" @click="reset">Reset</button>
  <button @click="start" :disabled="state.isPlaying">play</button>
  <Block v-if="state.isPlaying" :delay="state.delay" @end="endGame"/>
  <Result v-if="state.showResult" :score="state.score" :username="state.usarname"/>
</template>

<style>
@import './assets/base.css';

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem 0px;
  text-align: center;
  color: #38eba6;
  font-weight: normal;
}

button {
  background-color: #1effaf;
  color: rgb(41, 41, 41);
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
  font-weight: bold;
}

button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}

.reset{
  background-color: #ff1e69;
  color: #fff;
}

@media (min-width:480px) {
    
}
</style>
