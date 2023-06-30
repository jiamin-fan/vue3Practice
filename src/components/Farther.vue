<script setup>
import { ref } from 'vue';
import Son from './Son.vue';
const count = ref(100)
setInterval(()=>{
    count.value=200
},3000)

const getMsg= (msg)=>{
console.log(msg)
}
</script>
<template>
    <div class="farther">
        <h1>我是父组件</h1>
        <!-- 1.绑定属性  绑定事件-->
        <Son message="0" :count="count" @get-msg="getMsg"></Son>
    </div>
</template>
<style scoped>
.farther{
    width: 400px;
    height: 400px;
    border: 2px solid black;
}
</style>