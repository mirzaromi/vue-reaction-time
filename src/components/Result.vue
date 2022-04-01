<template>
    <p class="reaction">Your Reaction Time = {{score}} ms</p>
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
            ResultData.rank = `Super sekaliii, anda dapat merespon sesuatu yang bahkan belum terjadi`
        } 
        else if (ResultProp.score<400) {
            ResultData.rank = `boleh juga responnya, dengan respon secepat ini anda bisa menepuk lalat sebelum bergerak`
        } else {
            ResultData.rank = `Respon anda lambat, gak heran kalo doi sudah hilang`
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