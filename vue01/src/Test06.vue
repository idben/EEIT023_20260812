<script setup>
import { ref, computed } from 'vue'

const firstName = ref('John')
const lastName = ref('Doe')

// computed 的唯讀寫法
// const fullName = computed(() => `${firstName.value} ${lastName.value}`)

const fullName = computed({
    get() {
        // return `${firstName.value} ${lastName.value}`
        // ['Ben', 'Chen'].join(' ') // 'Ben Chen'
        // ['Ben', ''].join(' ') // 'Ben '
        // ['Ben', ''].fileter(Boolean).join(' ') // 'Ben'
        return [firstName.value, lastName.value].filter(Boolean).join(' ')
    },
    set(newValue) {
        console.log(newValue);
        const nameAry = newValue.split(' ')
        firstName.value = nameAry[0] || ''
        lastName.value = nameAry[1] || ''
    }
})
</script>

<template>
    <h1>computed 的進階用法 (setter/getter)</h1>
    <div>名: <input type="text" v-model="firstName"></div>
    <div>姓: <input type="text" v-model="lastName"></div>
    <div>全名: <input type="text" v-model="fullName"></div>
    <p>目前的全名: {{ fullName }}</p>
</template>

<style scoped></style>