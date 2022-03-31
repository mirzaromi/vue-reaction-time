<template>
    <div class="block" v-if="data.showBlock" @click="stopTimer">click me</div>
</template>

<script setup>
import { onMounted, onUpdated, reactive } from 'vue';
const prop = defineProps(["delay"])
const data = reactive({
    showBlock: false,
    timer: null,
    reactionTime: 0,
})
const emit = defineEmits(['end'])
onMounted(() => {
    // console.log(`the component is now mounted.`)
    setTimeout(() => {
        data.showBlock = true
        startTimer()
    }, prop.delay)
})
onUpdated(() => {
    // console.log(`updated`)
})
function startTimer() {
    data.timer = setInterval(() => {
        data.reactionTime += 10
    }, 10)
}
function stopTimer() {
    clearInterval(data.timer)
    emit('end', data.reactionTime)
    console.log(data.reactionTime)
}

</script>

<style>
.block {
    width: 400px;
    border-radius: 20px;
    background-color: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
@media (max-width: 480px) {
    .block {
    width: 300px;

}
}
</style>