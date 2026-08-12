<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const height = ref(window.innerHeight)
const width = ref(window.innerWidth)
const time = ref('')
let timer = null

const handleResize = () => {
    width.value = window.innerWidth
    height.value = window.innerHeight
}

onMounted(() => {
    console.log("元件已掛載");
    window.addEventListener('resize', handleResize)
    timer = setInterval(() => {
        // Date.now()
        const now = new Date()
        time.value = now.toLocaleTimeString()
        console.log(`每秒執行一次 ${now.getTime()}`);

    }, 1000)
})

onUnmounted(() => {
    console.log("元件已卸載");
    window.removeEventListener('resize', handleResize)
    clearInterval(timer)
})

</script>

<template>
    <h2>子元件 - 生命週期 hooks 的觀察</h2>
    <p>視窗寬度: {{ width }}</p>
    <p>視窗高度: {{ height }}</p>
    <p>更新時間: {{ time }}</p>
</template>

<style scoped></style>