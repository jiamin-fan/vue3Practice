<script setup>
import { onMounted, ref } from 'vue';
import Son from './Son.vue';
const count = ref(100)
setInterval(()=>{
    count.value=200
},3000)

const getMsg= (msg)=>{
console.log(msg)
}

// 1.调用ref函数 ->ref对象，以便于引用模板
const h1Ref =  ref(null)
const sonRef = ref(null)

// 组件挂载完毕之后才能获取
onMounted(()=>{
    console.log(h1Ref.value)
    console.log(sonRef.value)
})
</script>
<template>
    <div class="farther">
        <h1 ref="h1Ref">我是父组件</h1>
        <!-- 1.绑定属性  绑定事件   通过ref标识绑定ref对象-->
        <Son message="0" :count="count" @get-msg="getMsg" ref="sonRef"></Son>
    </div>
</template>
<style scoped>
.farther{
    width: 400px;
    height: 400px;
    border: 2px solid black;
}
</style>