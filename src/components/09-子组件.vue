<template>
  <p>这是子组件:{{ num }}</p>
</template>

<script setup lang="ts">
import { defineProps } from "vue"
defineProps({
  num: {
    type: Number,
    default: 0
  }
})

</script>

<style lang="less" scoped>
</style>