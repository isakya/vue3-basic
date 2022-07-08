<template>
  <p>这是子组件:{{ num }}</p>
  <button @click="hdClick">子传父</button>
</template>

<script setup lang="ts">
import { defineProps, defineEmits } from "vue"
defineProps({
  num: {
    type: Number,
    default: 0
  }
})

// 子传父的时候需要先定义好emit这个方法
const emit = defineEmits<{
  (event: 'fn', n: number): void,
}>()

let hdClick = () => {
  // 以前通过$emit
  emit('fn', 10)
}
</script>

<style lang="less" scoped>
</style>