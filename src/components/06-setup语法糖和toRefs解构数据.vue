<template>
  <h3>setup语法糖和toRefs解构数据</h3>
  <p>{{ num }}</p>
  <button @click="num++">++</button>
  <button @click="hdClick">hdClick++</button>
</template>

<script setup lang="ts">
// setup 语法加上之后，script之间的代码会被Vue内部自动添加到原先的setup方法中
import { reactive, toRefs } from "vue"
let obj = {
  num: 20
}


/**
 * 解构reactive中的数据
 * 注意：解构后的数据需要用 .value 来访问，在setup中导出的话还是直接导出 num ，不用.value
 */
let objRet = reactive(obj)
// 解构数据，更方便使用
let { num } = toRefs(objRet)

// // 或者这样解构
// let { num } = toRefs(reactive(obj))


let hdClick = () => {
  num.value++
}

</script>

<style lang="less" scoped>
</style>