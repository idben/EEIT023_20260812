<script setup>
import { ref } from 'vue'

const users = ref([
    { id: 1, name: '小明', role: '前端' },
    { id: 2, name: '小華', role: '後端' },
    { id: 3, name: '小美', role: '設計' },
]);
</script>


<template>
    <ul>
        <li v-for="(user, index) in users" :key="index">
            <slot :user="user" :index="index"></slot>
        </li>
    </ul>
</template>

<style scoped></style>