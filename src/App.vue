<template>
  <div id="app">
    <h1 style="color: red;">父组件</h1>
    小明的爸爸现在有{{ money }}元
    <h2>不使用sync修饰符</h2>
    <!-- 一定会触发这个事件：@update:变量名="money = $event" 这是固定写法 -->
    <Child :money="money" @update:money="money = $event"></Child>

    <h2>使用sync修饰符</h2>
    <Child :money.sync="money"></Child>

    <h2>使用v-model修饰符</h2>
    <Child2 :value="money" @input="money = $event"></Child2>
    <Child2 v-model="money"></Child2>
  </div>
</template>

<script>
import Child from './components/Child.vue'
import Child2 from './components/Child2.vue'
export default {
  name: 'App',
  components: {
    Child,
    Child2,
  },
  data() {
    return {
      money: 1000,
    }
  },
}
</script>

<style>
ul,
li {
  list-style: none;
  padding: 0;
}
.router-link-exact-active {
  background-color: green;
  color: white;
  padding: 3px;
}
.router-link-active {
  background-color: green;
  color: white;
}
</style>
