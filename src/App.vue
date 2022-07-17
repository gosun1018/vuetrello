<template>
  <div id="app">
    <Navbar />
    <router-view></router-view>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
export default {
  components: { Navbar },
  name: 'app',
  
  data () {
    return {
      msg: 'Welcome to Your Vue.js App '
    }
  }
}
</script>

<style>

</style>
