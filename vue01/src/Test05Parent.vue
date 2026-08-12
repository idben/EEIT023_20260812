<script setup>
import { ref } from 'vue'
import Test05 from './Test05.vue';

const showCheck = ref(true)
</script>

<template>
    <h1>父層元件 - 觀察元件的卸載和掛載</h1>
    <button @click="showCheck = !showCheck">切換</button>
    <Test05 v-if="showCheck" />
</template>

<style scoped></style>