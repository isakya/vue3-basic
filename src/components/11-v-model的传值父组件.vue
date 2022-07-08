<template>
  <h3>v-model的传值</h3>
  <Child v-model:num="num" />
</template>

<script setup lang="ts">
import Child from './11-v-model的传值子组件.vue'
import { reactive, toRefs, ref } from "vue"

let num = ref(20)

</script>

<style lang="less" scoped>
</style>