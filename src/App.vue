<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <Excel1 msg="Welcome to Your Vue.js App"/> -->
    <Excel3 />
  </div>
</template>

<script>
// import Excel1 from './components/Excel1.vue'
// import Excel2 from './components/Excel2.vue'
import Excel3 from './components/Excel3.vue'

export default {
  name: 'App',
  components: {
    // Excel1,
    // Excel2,
    Excel3,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
