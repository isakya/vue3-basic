<template>
  <h3>计算属性的用法</h3>
  <p>{{ dbNum }}</p>
  <button @click="num++">db</button>
  <p>obj:{{ dbNum2 }}</p>
  <button @click="objRet.num1++">obj++</button>
</template>

<script setup lang="ts">
import { ref, computed, reactive } from "vue"
/**
 * 基本数据
 */
let num = ref(20)
// 返回值就是计算属性的值
let dbNum = computed(() => {
  return num.value * 2
})

/**
 * 复杂数据
 */
let obj = {
  num1: 30
}
let objRet = reactive(obj)
let dbNum2 = computed(() => {
  return objRet.num1 * 2
})

</script>

<style lang="less" scoped>
</style>