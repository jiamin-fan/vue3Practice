<!-- 添加setup标识支持Composition API -->
<!-- <script >
export default{
  setup(){
    const message = 'this is a message!'
    console.log(message)
    const logMessage = ()=>{
      console.log(message)
    }
   return{
    message,
    logMessage
   }
  },
  beforeCreate(){
    console.log('this is beforeCreate')
  }
}
</script> -->

<!-- 语法糖写法 -->
<script setup>
const message ='This is a message!'
const logMessage=()=>{
  console.log(message)
}
</script>

<template>
  <div>
    {{ message }}
 <button @click="logMessage">A</button>
  </div>
 
</template>

<style scoped>


</style>
