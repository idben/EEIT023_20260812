<script setup>
const props = defineProps({
    name: {
        type: String,
        required: true
    }
})

const emit = defineEmits([
    'greet',
    'remove'
])
</script>

<template>
    <h3>子元件 - 向上傳資料的範例</h3>
    <p>名字: {{ name }}</p>
    <button @click="emit('greet', props.name)">打招呼</button>
    <button @click="emit('remove', props.name)">移除</button>
</template>

<style scoped></style>