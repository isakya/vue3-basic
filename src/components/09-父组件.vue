<template>
  <Child :num="num"></Child>
</template>

<script setup lang="ts">
import Child from './09-子组件.vue'
import { reactive, toRefs, ref } from "vue"
let num = ref(20)


</script>

<style lang="less" scoped>
</style>