<template>
    <p class="reaction">Selamat {{ResultProp.username}} Reaction Time kamu adalah {{ResultProp.score}} ms</p>
    <p class="rank">{{ResultData.rank}}</p>
</template>

<script setup>
import { reactive } from "@vue/reactivity"
import { onMounted } from "@vue/runtime-core"

    const ResultData = reactive({
        rank:null,
    })
    const ResultProp = defineProps(["score", "username"])

    onMounted(() => {
        if (ResultProp.score<250) {
            ResultData.rank = `Super sekaliii, ${ResultProp.username} dapat merespon sesuatu yang bahkan belum terjadi`
        } 
        else if (ResultProp.score<400) {
            ResultData.rank = `boleh juga responnya, dengan respon secepat ini ${ResultProp.username} bisa menepuk lalat sebelum bergerak`
        } else {
            ResultData.rank = `Respon ${ResultProp.username} lambat, gak heran kalo doi sudah hilang`
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