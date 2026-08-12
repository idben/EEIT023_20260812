<script setup>
const props = defineProps({
    name: {
        type: String,
        required: true
    },
    age: {
        type: Number,
        default: 18
    },
    greetingMessage: {
        type: String,
        default: ''
    }
})

</script>

<template>
    <h3>子元件</h3>
    <p>姓名: {{ name }}</p>
    <p>年齡: {{ age }}</p>
    <p>訊息: {{ greetingMessage }}</p>
</template>

<style scoped></style>