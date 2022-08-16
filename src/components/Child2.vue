<template>
  <div>
    <h1 style="color: red;">son2</h1>
    <span>小明每次花100元</span>
    <!-- @click="$emit('input', value - 100) 这里面的input不能改，只能是触发input -->
    <button @click="$emit('input', value - 100)">花钱</button>
    爸爸还剩{{ value }}元
  </div>
</template>

<script>
export default {
  /* 
    在子组件中使用v-model，子组件接收要使用value
    刚才使用money接收，直接不出结果
  */
  props: ['value'],
}
</script>

<style></style>
