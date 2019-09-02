<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
<!--    <Counter msg="点击按钮实现数字加减"/>-->
    <CounterGroup />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Counter from './components/Counter.vue'
import CounterGroup from './components/CounterGroup.vue'


export default {
  name: 'app',
  components: {
    CounterGroup,
    // HelloWorld,


  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
