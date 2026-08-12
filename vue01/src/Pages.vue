<script setup>
import { ref } from 'vue'
import Test05 from './Test05.vue'
import Cart from './Cart.vue'

const page = ref('main')
</script>

<template>
    <h1>多頁的切換, Vue Router 的原型</h1>
    <nav>
        <button @click="page = 'main'">主頁</button>
        <button @click="page = 'cart'">購物車</button>
    </nav>
    <Test05 v-if="page == 'main'" />
    <Cart v-if="page == 'cart'" />
</template>

<style scoped></style>