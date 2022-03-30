<template>
    <p class="reaction">Reaction Time = {{score}} ms</p>
    <p class="rank">{{ResultData.rank}}</p>
</template>

<script setup>
import { reactive } from "@vue/reactivity"
import { onMounted } from "@vue/runtime-core"

    const ResultData = reactive({
        rank:null,
    })
    const ResultProp = defineProps(["score"])

    onMounted(() => {
        if (ResultProp.score<250) {
            ResultData.rank = `Ninja Finger`
        } 
        else if (ResultProp.score<400) {
            ResultData.rank = `Rapid Reflex`
        } else {
            ResultData.rank = `Snail Pace`
        }
    })
</script>

<style>
    .reaction {
        margin: 20px auto;
        color: white;
        font-size: 1em;
    }
    .rank{
        font-size: 2em;
        font-weight: bold;
    }
</style>