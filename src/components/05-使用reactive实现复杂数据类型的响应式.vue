<template>
  <h3>使用reactive实现复杂数据类型的响应式</h3>
  <p>{{ objRet.num }}</p>
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue"

export default defineComponent({
  setup() {
    let obj = {
      num: 20
    }

    // 使用场景
    // ref 用来实现基础数据的响应式
    // reactive 用来实现复杂数据的响应式

    // 本质上两者就是相差一个 .value 的区别

    let objRet = reactive(obj)
    console.log(objRet.num);

    return {
      objRet
    };
  },
});
</script>

<style lang="less" scoped>
</style>