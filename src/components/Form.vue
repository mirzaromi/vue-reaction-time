<template>
    <form action="" class="form">
        <div class="form-wrapper">
            <p>Kasih Tau Namamu yaa!</p>
            <input type="text" class="input" v-model="formData.nama" placeholder="Input Nama">
            <br>            
            <button class="btn" @click="nextPage">Lanjut</button>
        </div>
    </form>
</template>

<script setup>
import { reactive } from 'vue';

const formData = reactive({
    nama: null,

})
const formEmit = defineEmits(['next'])
function nextPage() {
    formEmit('next', formData.nama)
}
</script>

<style>
    .form{
        height: 100vh;
        width: 100%;
        background-color: #020e09;
        margin: 0;
        position: absolute;
        z-index: 1;
    }

    .form-wrapper{
        margin: 100px auto;
    }

    .form p {
        font-size: 2rem;
        padding: 20px;
    }

    .form .input {
        background-color: #dcf1e8;
        width: 200px;
        height: 40px;
        border: none;
        border-radius: 7px;
        margin-bottom: 40px;
        text-align: center;
        font-size: 1.25rem;
        font-weight: 500;
    }

    .form .input:focus{
        border: 1px solid #1bcf84;

    }

    .form .input:focus-visible{
        outline: none;
    }

    .form .btn {
        width: 100px;
    }
</style> -->