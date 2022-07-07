<template>
  <div>ref方法（操作基本数据类型的数据，响应式数据）</div>
  <p>{{ num }}</p>
  <button @click="hdClick">按钮</button>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue"

export default defineComponent({
  setup() {

    // 直接定义不是响应式数据,无法做到双向数据绑定
    // let num = 20

    /**
     * 1. 这里的num是Vue内部封装的一个响应式数据
     * 2. num.value 才能真正拿到 20 这个数据
     * 3. 操作num数据时，需要 .value 
     * 4. 模板上依旧使用 num，因为Vue在编译模板的时候已经帮我们 .value 获取值了
     */
    let num = ref(20)
    const hdClick = () => {
      num.value++
      console.log(num);
    }

    return {
      num,
      hdClick
    };
  },
});
</script>

<style lang="less" scoped>
</style>