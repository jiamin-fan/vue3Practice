<script setup>
// 2.defineProps接收数据  通过defineEmits()->emit(this.$emit)
const props = defineProps({message:String,count:Number})
const emit = defineEmits(['get-msg'])
const sendMsg = ()=>{
    // 触发自定义时间，传数据给父组件
    emit('get-msg','this is son message')
}

// 显示暴露子组件的内部属性和方法
defineExpose({
    sendMsg,
    emit,
   
})
</script>
<template>
    <div class="son">
        <h2>我是子组件</h2>
        <div>
            父组件传入的数据-{{ message }}-{{ count }}
        </div>
        <div>
            <button @click="sendMsg">触发自定义事件</button>
        </div>
    </div>
</template>
<style scoped>
.son{
    width: 200px;
    height: 200px;
    border: 1px solid black;
}
</style>