<script setup>
import { inject } from 'vue';

const topData = inject('data-key')
const countData = inject('count-key')
const  add = inject('setCount-key')
</script>

<template>
    <div class="bottom">
        <h1>我是Bottom组件</h1>
        <p>来自顶层组件的数据：{{ topData }}</p>
        <p>来自顶层的响应式数据：{{ countData }}</p>
        <button @click="add">改变顶层组件的数据</button>
    </div>
</template>

<style scoped>
.bottom{
    border: 1px solid blue;
    margin: 20px;
}
</style>