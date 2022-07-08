<template>
  <!-- 具名插槽 -->
  <slot name="btn"></slot>
  <p>子组件</p>
  <slot></slot>
</template>

<script setup lang="ts">
import { reactive, toRefs, ref } from "vue"

</script>

<style lang="less" scoped>
</style>