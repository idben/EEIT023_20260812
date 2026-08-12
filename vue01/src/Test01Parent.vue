<script setup>
import Test01 from './Test01.vue'
</script>

<template>
    <h1>父層元件</h1>
    <Test01 name="Ben" :age="40" />
    <hr>
    <Test01 />
</template>

<style scoped></style>