<script setup>
import { ref, watch, computed } from 'vue'

const count = ref(0)
const message = ref('')
const totalMoney = ref(750)
const messageCart = ref('')
const fistName = ref('')
const lastName = ref('')
const freeShipping = 1000

watch(count, (newV, oldV) => {
    message.value = `count 從 ${oldV} 變成 ${newV}`
})

const remainingAmount = computed(() => {
    return Math.max(freeShipping - totalMoney.value, 0)
    // 1000 - 750 = 250, 0
    // 1000 - 850 = 150, 0
    // 1000 - 950 = 50, 0
    // 1000 - 1050 = -50, 0
})

watch(remainingAmount, (amout) => {
    if (amout == 0) {
        messageCart.value = `恭喜獲得免運`
    } else {
        messageCart.value = `再買 ${amout} 元即可免運`
    }
}, {
    immediate: true
})

watch([fistName, lastName], ([newFirst, newLast], [oldFirst, oldLast]) => {
    console.log(`姓名從 ${oldFirst} ${oldLast} 變成 ${newFirst} ${newLast}`);

})

const message3 = computed(() => {
    if (remainingAmount.value == 0) return '恭喜獲得免運'
    return `再買 ${remainingAmount.value} 元即可免運`
})

// computed: 負責算出東西來
// watch: 負責指定資料改變後做些什麼事的
// watch 是有副作用的時候才需要使用
// 副作用 side effect 是什麼? 一段程式除了計算與回傳內容外, 還有改變外部的狀態, 或是影響本段程式外的內容, 就叫做有副作用
// 簡單的來說, 監聽某個變數變化, 去呼叫 api, 這個就是副作用
// watch(source, (新值, 舊值, 清理函數)=>{})
// watch 如果需要立即執行的話, 需要第三個參數中的 immediate 屬性設為 true
</script>

<template>
    <h1>測試 watch</h1>
    <button @click="count++">count: {{ count }}</button>
    <p>{{ message }}</p>
    <br><br>
    <hr>
    <h1>以購物車(免運)為範例</h1>
    <p>總金額: {{ totalMoney }}</p>
    <p>{{ message3 }}</p>
    <button @click="totalMoney += 100">加購 100 元商品</button>
    <br><br>
    <hr>
    <h1>watch 複數對象</h1>
    <input type="text" v-model="fistName">
    <input type="text" v-model="lastName">
</template>

<style scoped></style>