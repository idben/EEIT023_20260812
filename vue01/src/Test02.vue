<script setup>
const props = defineProps({
    name: {
        type: String,
        required: true
    }
})

// 需要驗證時, emit 改物件寫法
// null 不需要驗證
// 接驗證 function
// 缺少參數警告的寫法
const emit = defineEmits({
    greet: (name) => {
        // 驗證 function 最後就是回傳過與不過的 true/false
        if (!name) {
            console.warn('greet 事件缺少 name 參數');

            return false
        }
        return true
    },
    remove: null
})

// 缺少參數不傳的寫法
const handleGreet = (name) => {
    if (!name) {
        console.error('greet 事件缺少 name 參數');
        return
    }
    // 最後
    emit('greet', name)
}

const handleGreet2 = function () {
    if (!props.name) {
        console.error('greet 事件缺少 props.name');
        return
    }
    // 最後
    emit('greet', props.name)
}
</script>

<template>
    <h3>子元件 - 向上傳資料的範例</h3>
    <p>名字: {{ name }}</p>
    <!-- <button @click="emit('greet')">打招呼</button> -->
    <!-- 缺少參數不傳 -->
    <!-- <button @click="handleGreet(props.name)">打招呼</button> -->
    <button @click="handleGreet2">打招呼</button>
    <button @click="emit('remove', props.name)">移除</button>
</template>

<style scoped></style>