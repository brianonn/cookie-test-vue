<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <!-- CookieNotice can include a custom message -->
    <CookieNotice cookieName="mytest">
      This is the Cookie Notice. We use Cookies on this website. Click if you agree ->>&nbsp;
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
  color: #5c3e50;
  margin-top: 60px;
}
</style>
