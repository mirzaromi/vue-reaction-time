<template>
    <form action="" class="form">
        <div class="form-wrapper">
            <p>Kasih Tau Namamu yaa!</p>
            <input type="text" class="input">
        </div>
    </form>
</template>

<script setup>
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
        height: 30px;
        border: none;
    }

    .form .input:focus{
        border: 1px solid #1bcf84;

    }

    .form .input:focus-visible{
        outline: none;
    }
</style>