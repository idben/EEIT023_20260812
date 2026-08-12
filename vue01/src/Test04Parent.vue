<script setup>
import Test04 from './Test04.vue'
</script>

<template>
    <h1>作用域插槽</h1>
    <Test04>
        <template #default="{ user, index }">
            {{ index + 1 }}. {{ user.name }}
        </template>
    </Test04>
    <hr>
    <Test04>
        <template #default="{ user, index }">
            {{ user.name }} - {{ user.role }}
        </template>
    </Test04>
</template>

<style scoped></style>