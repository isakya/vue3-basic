<template>
  <Child :num="num" @fn="changeNum"></Child>
</template>

<script setup lang="ts">
import Child from './09-子组件.vue'
import { reactive, toRefs, ref } from "vue"
let num = ref(20)

// 子传父
const changeNum = (n: number) => {
  num.value += n + 1
}

</script>

<style lang="less" scoped>
</style>