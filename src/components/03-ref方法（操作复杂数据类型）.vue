<template>
  <div>ref方法（操作复杂数据类型）</div>
  <p>{{ objRef.num }}</p>
  <button @click="objRef.num++">++</button>
  <button @click="hdClick">hdClick++</button>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue"

export default defineComponent({
  setup() {
    let obj = {
      num: 30
    }
    // 取值需要 对象.value.xxx
    let objRef = ref(obj)
    let hdClick = () => {
      objRef.value.num++
    }
    return {
      objRef,
      hdClick
    };
  },
});
</script>

<style lang="less" scoped>
</style>