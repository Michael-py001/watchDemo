<script setup>
import { ref ,watch } from 'vue'

const props = defineProps({
  arr: Array
})
//
watch(props.arr,(arr)=>{
  console.log("HelloWorld-->使用props.arr：",arr)
})
watch(()=>props.arr,(arr)=>{
  console.log("HelloWorld-->使用函数返回值,arr改变：",arr)
})
</script>

<script>
  export default {
    props:{
      arr:Array
    },
    watch: {
      arr(value) {
        console.log("option选项的watch：",value)
      }
    }
  }
</script>

<template>
  HelloWorld --> {{arr}}
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
