<script setup>
import { ref } from 'vue'

const name = ref('')
const message = ref('')
const password = ref('')
const age = ref('')
</script>

<template>
    <div>
        <h1>文字與密碼</h1>

        <div>
            <label>姓名: </label>
            <input type="text" v-model="name" placeholder="請輸入姓名">
            <p>{{ name }}</p>
        </div>

        <div>
            <label>訊息: </label>
            <textarea v-model="message" rows="4"></textarea>
            <p>{{ message }}</p>
        </div>

        <div>
            <label>密碼: </label>
            <input type="password" v-model="password" placeholder="請輸入密碼">
            <p>{{ password }}</p>
        </div>


        <div>
            <label>年齡: </label>
            <input type="number" v-model="age" placeholder="請輸入年齡">
            <p>{{ age }} (型別: {{ typeof age }})</p>
        </div>
    </div>
</template>

<style scoped></style>