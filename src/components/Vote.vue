<template>
  <div>
    <h3>{{title}}</h3>
    <div>
      <p>{{num}}</p>
      <p>{{num1}}</p>
      <button @click="changeFn">支持</button>
      <button @click="changeFn2">反对</button>
    </div>
  </div>
</template>

<script>
import { watchEffect, ref, reactive, toRefs, readonly, watch } from 'vue'
export default {
  props: {
    title: String
  },
  // setup执行在初始化props与beforeCreate之间
  setup(props) {
    let state = reactive({
      num: 1,
      num1: 2
    })
    const changeFn = () => {
      state.num++
    }
    const changeFn2 = () => {
      state.num1++
    }
    watchEffect(() => {
      console.log(state.num)
    })
    watchEffect(() => {
      console.log(state.num)
    })
    // watch(state, () => {
    //   console.log(state)
    // })
    return {
      changeFn,
      changeFn2,
      ...toRefs(state),
    }
  }
}
</script>
