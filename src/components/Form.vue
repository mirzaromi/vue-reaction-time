<template>
    <div class="wrapper">
        <form action class="form" @submit.prevent="nextPage">
            <div class="form-wrapper">
                <p>Kasih Tau Namamu yaa!</p>
                <input type="text" class="input" v-model="formData.nama" placeholder="Input Nama" />
                <p v-if="formData.warning" class="error">Nggak boleh kosong yaa</p>
                <br />
                <button class="btn" type="submit">Lanjut</button>
            </div>
        </form>
        <div class="rule">
            <h1>Lihat Aturan Mainnya yaa</h1>
            <ol>
                <li>aaaa</li>
            </ol>
        </div>
    </div>
</template>

<script setup>
import { reactive } from 'vue';

const formData = reactive({
    nama: null,
    warning: false
})
const formEmit = defineEmits(['next'])
function nextPage() {
    if (formData.nama == null || formData.nama == "") {
        formData.warning = true
    } else {
        formEmit('next', formData.nama)
        formData.warning = false
    }
}
</script>

<style>
.wrapper {
    height: 100vh;
    width: 100%;
    background-color: #020e09;
    margin: 0;
    position: absolute;
    z-index: 1;
}

.form-wrapper {
    margin: 80px auto 0 auto;
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

.form .input:focus {
    border: 1px solid #1bcf84;
}

.form .input:focus-visible {
    outline: none;
}

.form .btn {
    width: 100px;
}
p.error {
    color: rgb(255, 61, 136);
    font-size: 0.95rem;
    margin: -50px auto 0px auto;
}

.rule{
    margin: 20px;
    padding: 20px;
    border-radius: 10px;
    background-color: #1bcf8485;
    color: #fff;
}

.rule h1{
    font-size: 22px;
}
</style> -->