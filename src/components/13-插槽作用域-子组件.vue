<template>
  <slot name="btn" title="hello"></slot>
  <p>子组件</p>
  <slot></slot>
</template>

<script setup lang="ts">
import { reactive, toRefs, ref } from "vue"

</script>

<style lang="less" scoped>
</style>