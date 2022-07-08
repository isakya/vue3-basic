<template>
  <h3>watch的写法 和 watchEffect</h3>
  <p>{{ num }}</p>
  <!-- <p>{{ num1 }}</p> -->
  <p>{{ objRet.num1 }}</p>
  <button @click="num++">num</button>
  <!-- <button @click="num1++">num1</button> -->
  <button @click="objRet.num1++">num1</button>
</template>

<script setup lang="ts">
import { ref, watch, reactive, toRefs, watchEffect } from "vue"
let num = ref(20)

/**
 * 注意：监听的数据也必须是响应式数据
 */
watch(num, (newValue, oldValue) => {
  console.log(newValue, oldValue);
})

/**
 * 复杂数据的写法:两种写法
 * 
 */
let obj = {
  num1: 30,
  num2: 20
}

// 1. 有解构时
// let { num1 } = toRefs(reactive(obj))
// watch(num1, (newVal, oldVal) => {
//   console.log(newVal, oldVal);
// })

// 2. 没有解构时
let objRet = reactive(obj)
// watch(() => objRet.num, (newVal, oldVal) => {
//   console.log(newVal, oldVal);
// })
// 监听多个数据时
watch([() => objRet.num1, () => objRet.num2], (newVal, oldVal) => {
  console.log(newVal, oldVal);
})

/**
 * 在页面刷新的时候就立即监听 等同vue2 的immediate：true
 */
watchEffect(() => {
  // 凡是写在这里的数据，只要发生变化，都会触发这里的代码执行
  console.log(objRet.num1);
})

/**
 * 总结：
 * ①有要用到新旧值时用 watch
 * ②当有多个数据需要监听时用 watchEffect
 */
</script>

<style lang="less" scoped>
</style>