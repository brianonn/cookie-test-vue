
// this is untested code

// This Vue component puts a cookie notice on the bottom right of the screen

// TODO: default the div to display:none, check for the cookie, only display 
//       the div block if the cookie is not already set
// TODO: add a link to a cookie policy or privacy policy page. 

// for splitting the code into separate files, see here:
// https://codeburst.io/vue-components-with-pug-and-stylus-556508b74c96
// 

<!-- <template src="./template.pug" lang="pug"></template> -->
// for native events on the DOM, v-on:click changes to v-on:click.native in Vue V2
<template lang="pug">
  #cookieNotice(v-show="showBanner" v-on:click="clickHandler")
    slot {{ message }}
    a(href="#" v-on:click="clickHandler" class="button") {{ OK }}
</template>

<!-- <script src="./script.js"></script> -->
<script>
export default {
  name: 'CookieNotice',
  props: ['cookieName', 'secure'],
  data() {
    return {
      message: 'This website uses cookies. Click here to accept: ',
      OK: 'OK',
      showBanner: false,
      defaultCookieName: 'jHKcRZGxyNLZuY8Y'
    }
  },
  created() {
    var regex = new RegExp(`^(.*;)?\\s*${this.theCookieName}\\s*=\\s*[^;]+(.*)?$`)
    this.showBanner = !document.cookie.match(regex) // show the banner if there is no matching cookie in the DOM
    console.log(`this.httpOnly = ${this.httpOnly}`)
    console.log(`this.useHttpOnly = ${this.useHttpOnly}`)
  },
  methods: {
    clickHandler: function() {
      console.log('click')
      var now  = new Date()
      var time = now.getTime()
      time += 365*86400000
      now.setTime(time)
      document.cookie = `${this.theCookieName}=1; expires=${now.toUTCString()};${this.useSecure?'secure':''}`
      this.showBanner = false;
      return false
    }
  },
  computed: {
    // either the property value of the default value
    theCookieName: function () {
      return this.cookieName ? this.cookieName : this.defaultCookieName;
    },
    useSecure: function () {
      return !! (this.secure == "" || this.secure && (this.secure.toLowerCase() == 'yes' || this.secure.toLowerCase() == 'true'))
    }
  }
}
</script>

<!-- <style src="./style.styl" lang="stylus"></style> -->
<style lang="stylus" scoped>
#cookieNotice
  position fixed
  bottom   0px
  right    0px
  padding  0.5em
  background-color #000
  color    #fff
  z-index  9999999
  border   1px solid #aaa
  opacity  0.8
  text-align center
.button
  color    #fff
  padding  5px
  padding-top 6px
  padding-bottom 0px
  border   1px solid #00b300
  border-radius 5px
  background-color #00b300
  text-decoration none
  vertical-align bottom
  text-align center
  line-height 16px
</style>

