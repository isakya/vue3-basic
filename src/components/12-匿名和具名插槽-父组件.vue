<template>
  <h3>匿名插槽和具名插槽</h3>
  <Child>
    <!-- 具名 -->
    <template v-slot:btn>
      <button>按钮</button>
    </template>
    <!-- 匿名 -->
    <a href="#">a标签</a>
  </Child>
</template>

<script setup lang="ts">
import Child from './12-匿名和具名插槽-子组件.vue'
import { reactive, toRefs, ref } from "vue"

</script>

<style lang="less" scoped>
</style>