<script setup>
const props = defineProps({
    name: {
        type: String,
        required: true
    },
    age: {
        type: Number,
        default: 18
    }
})

</script>

<template>
    <h3>子元件</h3>
    <p>姓名: {{ name }}</p>
    <p>年齡: {{ age }}</p>
</template>

<style scoped></style>