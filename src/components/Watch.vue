<script setup>
import {ref,watch} from  'vue'
const count = ref(0)
const changeCount = ()=>{
    count.value++
}

const name = ref('cp')
const changeName = ()=>{
    name.value = 'pc'
}

// watch侦听单个数据源
// watch(count,(newValue,oldValue)=>{
    
//     console.log('count变化了',newValue,oldValue)
// })

// watch侦听多个数据源
// watch([count,name],([newCount,newName],[oldCount,oldName])=>{
//     console.log('count或name发生变化了->',[newCount,newName],[oldCount,oldName])
// })

// 开启即刻监听
// watch(count,(newValue,oldValue)=>{
    
//     console.log('count变化了',newValue,oldValue)
// },{immediate:true})

const state = ref({gender:0, age:20})
const changeState = ()=>{
    state.value.gender++
    state.value.age++
}

// 深度监听嵌套属性的值
// watch(state,()=>{
//     console.log('state里的值发生了改变')
// },{deep:true})

watch(()=>state.value.age,()=>{
    console.log('state里的值发生了改变')
})
</script>
<template>
    <div><button @click="changeCount">{{ count }}</button></div>
    <div><button @click="changeName">{{ name }}</button></div>
    <div><button @click="changeState">改变嵌套对象属性的值{{ state }}</button></div>
</template>
<style scoped></style>