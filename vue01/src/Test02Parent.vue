<script setup>
import Test02 from './Test02.vue'

const onGreet = name => alert(`你好, ${name}`)

function onRemove(name) {
    alert(`移除, ${name}`)
}
</script>

<template>
    <h1>父層元件 - 向上傳資料的範例</h1>
    <Test02 name="小明" @greet="onGreet" @remove="onRemove" />
</template>

<style scoped></style>