<script setup>
import Test01 from './Test01.vue'
</script>

<template>
    <h1>父層元件</h1>
    <Test01 name="Ben" :age="40" greeting-message="abc" />
    <hr>
    <Test01 name="May" />
</template>

<style scoped></style>