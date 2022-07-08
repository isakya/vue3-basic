<template>
  <h3>插槽作用域：在父组件中的子组件标签内部，获取子组件的数据</h3>
  <Child>
    <!-- scope 获取对应的子组件slot标签中的所有属性，scope名字是自定义的 -->
    <template #btn="scope">
      <button>按钮\{{ scope.title }}</button>
    </template>
    <a href="#">a标签</a>
  </Child>
</template>

<script setup lang="ts">
import Child from './13-插槽作用域-子组件.vue'
import { reactive, toRefs, ref } from "vue"

</script>

<style lang="less" scoped>
</style>