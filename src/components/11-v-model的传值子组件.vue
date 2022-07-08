<template>
  <p>子组件: {{ num }}</p>
  <button @click="hdClick">++</button>
</template>

<script setup lang="ts">
import { reactive, toRefs, ref } from "vue"
let props = defineProps({
  num: {
    type: Number,
    default: 0
  }
})

const emit = defineEmits<{
  // update: 固定写法，后面是父组件中需要更新的值
  (event: 'update:num', n: number): void
}>()

let n = props.num
let hdClick = () => {
  emit('update:num', n++)
}
</script>

<style lang="less" scoped>
</style>