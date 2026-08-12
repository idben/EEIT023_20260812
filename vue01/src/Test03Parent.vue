<script setup>
import Test03 from './Test03.vue'
</script>

<template>
    <h1>插槽的設計與使用</h1>
    <Test03>
        <p>這一段放在預設插槽區</p>
        <template #header>
            <h2>卡片標題</h2>
        </template>
        <template #footer>
            <button>確認</button>
        </template>
    </Test03>
</template>

<style scoped></style>