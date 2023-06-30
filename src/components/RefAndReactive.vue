<script setup>
// //1、导入reactive函数
// import { reactive } from 'vue';

// //2、执行函数 传入一个对象类型的参数 变量接收
// const state = reactive({
//     count:0
// })

// const addCount = ()=>{
//     state.count++
// }


// 1、导入ref函数
import { ref } from 'vue';
// 2、执行函数 传入参数【简单类型/对象类型】 变量接收
const count = ref(0)

const addCount =()=>{
    // 脚本区域修改ref产生的响应式对象数据，必须通过.value属性
    count.value++
}

</script>

<template>
    <div>
        <!-- <button @click="addCount">{{ state.count }}</button> -->
        <button @click="addCount">{{ count }}</button>
    </div>
    
</template>

<style scoped></style>
