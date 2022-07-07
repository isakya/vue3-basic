<template>
  生命周期函数
  setup, onBeforeMount, onMounted
</template>

<script lang="ts">
import { defineComponent, onBeforeMount, onMounted } from "vue"
export default defineComponent({
  /**
   * setup 是生命周期函数，它代替了 beforeCreate 和 created
   */
  setup() {
    console.log('setup执行了1');

    onBeforeMount(() => {
      console.log('onBeforeMount执行了2');
    })

    onMounted(() => {
      console.log('onMounted执行了3');
    })
  }
})
</script>

<style lang="less" scoped>
</style>