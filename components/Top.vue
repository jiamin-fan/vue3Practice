<script setup>
import Middle from './Middle.vue';
import {provide, ref} from 'vue'

const count = ref(0)
// 1.顶层组件提供数据
provide('data-key','This is top data')
provide('count-key',count)

setTimeout(()=>{
    count.value = 200
},5000)

// 传递方法
const setCount = ()=>{
    count.value++
}
provide('setCount-key',setCount)
</script>

<template>
    <div class="top">
        <h1>我是Top组件</h1>
        <Middle></Middle>
    </div>
</template>

<style scoped>
.top{
    border: 2px solid orangered;
    
}
</style>