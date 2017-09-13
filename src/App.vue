<template>
  <div id="app" class='container'>
    <nav-bar></nav-bar>
    <router-view></router-view>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'

export default {
  name: 'app',
  components: {
  	NavBar
  },
  data () {
    return {}
  }
}
</script>
