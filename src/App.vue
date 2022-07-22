<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
import HelloWorldTwo from './components/HelloWorldTwo.vue'
import HelloWorldThree from './components/HelloWorldThree.vue'
import {ref} from 'vue'
let arr = ref([])
let arr2 = ref([])
let arr3 = ref([])

setTimeout(()=>{
  console.log("-----------------------")
  console.log('HelloWorld-直接赋值')
  arr.value = [1,2,3]
},1500)


setTimeout(()=>{
  console.log("-----------------------")
   console.log('HelloWorldTwo-使用push')
  arr2.value.push(1)
},2500)

setTimeout(()=>{
  console.log("-----------------------")
   console.log('HelloWorldThree-同时使用')
  arr3.value = [1,2,3]
  setTimeout(()=>{
     arr3.value.push(1) //这里不触发了
  },1000)
},3500)



</script>

<template>
  <HelloWorld :arr = "arr"/>
  <br/>
  <HelloWorldTwo :arr = "arr2"/>
  <br/>
  <HelloWorldThree :arr = "arr3"/>
</template>

<style>

</style>
