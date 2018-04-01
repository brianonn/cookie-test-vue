<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <!-- CookieNotice can include a custom message -->
    <CookieNotice cookieName="mytest">
      This is the EU Cookie Notice. Click if you agree.
    </CookieNotice>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import CookieNotice from './components/CookieNotice.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    CookieNotice
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
