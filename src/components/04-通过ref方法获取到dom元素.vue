<template>
  <h3>通过ref方法获取到dom元素</h3>
  <p ref="op">这是p标签</p>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted, nextTick } from "vue"

export default defineComponent({
  setup() {
    let op = ref() // 获取了ref属性的标签，且值为op的标签

    console.log('setup:', op.value) // undefined 拿不到p dom标签，是因为执行时机不对

    onMounted(() => {
      console.log('onMounted:', op.value) // 挂载完毕之后才能获取到dom元素
    })

    nextTick(() => {
      console.log('nextTick:', op.value); // 在下一次dom更新的时候执行（只会调用一次）
    })

    return {
      // 获取dom元素也必须要导出
      op
    };
  },
});
</script>

<style lang="less" scoped>
</style>