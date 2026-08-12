<script setup>
import { ref, watchEffect } from 'vue'

const count = ref(0)
const name = ref('vue')
const city = ref('kauhsiung')
const maxRent = ref(20000)
const petFriendly = ref(true)
const sort = ref('rent-asc')

watchEffect(() => {
    console.log(`count: ${count.value}`);
    // console.log(`名字變成: ${name.value}`);
})

watchEffect(() => {
    console.log(`名字變成: ${name.value}`);
})

watchEffect(() => {
    // 取得查詢參數的方法
    // console.log(location.search);
    // const params = new URLSearchParams(location.search)
    // console.log(params.get("a"));
    // console.log(params.get("b"));
    const params = new URLSearchParams()
    params.set('city', city.value)
    params.set('maxRent', String(maxRent.value))
    params.set('sort', sort.value)
    if (petFriendly.value) {
        params.set('petFriendly', '1')
    }

    history.replaceState(
        null,
        '',
        `${location.pathname}?${params.toString()}`
    )

    // call API
    // fetch("/api/rent", {method: "post"})
    // fetch 的資料會寫入一組響應式資料
    // 再使用這組響應式資料在 template 用 v-for 建立 table
})
// watchEffect 會立即執行一次, 不需設定
// 可以同時有複數組的 watchEffect 和 watch
// watchEffect((清理函數) => {})
</script>

<template>
    <div>
        <h1>watchEffect 的測試</h1>
        <button @click="count++">{{ count }}</button>
        <br>
        <input type="text" v-model="name">
        <br><br>
        <hr>

        <h1>watchEffect 並改變網址</h1>
        <div>
            <label>城市: </label>
            <select v-model="city">
                <option value="taipei">台北</option>
                <option value="taichung">台中</option>
                <option value="kauhsiung">高雄</option>
            </select>
        </div>
        <div>
            <label>最高租金: </label>
            <input type="number" step="500" v-model.number="maxRent">
        </div>
        <div>
            <label>可不可以養竉物: </label>
            <input type="checkbox" v-model="petFriendly">
        </div>
        <div>
            <label>排序方式: </label>
            <select v-model="sort">
                <option value="newest">最新刊登</option>
                <option value="rent-asc">租金由低到高</option>
                <option value="rent-desc">租金由高到低</option>
            </select>
        </div>
    </div>
</template>

<style scoped></style>