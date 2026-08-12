<script setup>
import { ref, onMounted, onUnmounted, onUpdated } from 'vue'

const count = ref(0)

onMounted(() => {
    console.log("購物車畫面 掛載 完成");
})

onUpdated(() => {
    console.log("購物車畫面 更新 完成");
})

onUnmounted(() => {
    console.log("購物車畫面 卸載 完成");
})
</script>

<template>
    <h2>購物車 - 觀察元件的卸載, 掛載和更新</h2>
    <button @click="count--">-</button>
    {{ count }}
    <button @click="count++">+</button>
</template>

<style scoped></style>