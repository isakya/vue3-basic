<template>
  <h3>全选/全不选案例</h3>
  <input type="checkbox" v-model="checkAll"> 全选/全不选
  <ul>
    <li v-for="(item, index) in list" :key="index">
      <input type="checkbox" v-model="checkList[index]">{{ item }}
    </li>
  </ul>
</template>

<script setup lang="ts">
import { reactive, toRefs, ref, computed } from "vue"
let { list, num, a, checkList } = toRefs(reactive({
  list: [10, 20, 30, 40],
  checkList: [false, true, false, false],
  num: 20,
  a: 30,
}))

let checkAll = computed({
  get() {
    /**
     * checkList包含有一个false 就返回false
     */
    return !checkList.value.includes(false)
  },
  set(newVal: boolean) {
    /**
     * checkAll被修改的时候
     */
    checkList.value = checkList.value.map(item => newVal)
  }
})



</script>

<style lang="less" scoped>
</style>