<script setup>
import Btn from '../components/Btn.vue';
</script>
<template>
    <div class="container mt-2">
        <Btn color="primary" dark size="large" rounded state="loading">Button is cool</Btn>
        <button class="button is-loading">Test button</button>
    </div>
</template>