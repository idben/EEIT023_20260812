<script setup>
import { ref, reactive, watch } from 'vue'

const user = reactive({
    name: '',
    email: ''
})
const log = ref('')

// 要使用回傳值的方式來指定監測對象
watch(() => user.name, (newV) => {
    log.value = "name 發生變化 " + newV
})
</script>

<template>
    <h1>監聽物件的特定屬性</h1>
    <div>
        <label for="">姓名</label>
        <input type="text" v-model="user.name">
    </div>
    <div>
        <label for="">郵件</label>
        <input type="text" v-model="user.email">
    </div>
    <p>{{ log }}</p>
    <div>
        {{ user }}
    </div>
</template>

<style scoped></style>