<template>
  <div>
    <div>
      Board
    </div>
    <div>
      {{bid}}
    </div>
    <router-link :to="`/board/${bid}/c/1`">card 1</router-link>
    <router-link :to="`/board/${bid}/c/2`">card 2</router-link>
    <router-link :to="`/board/${bid}/c/3`">card 3</router-link>
    <router-link :to="`/board/${bid}/c/4`">card 4</router-link>
    <router-view></router-view>
  </div>  
</template>

<script>
export default {
  data() {
    return {
      bid: 0
    }
  },
  created() {
    this.bid = this.$route.params.bid;
  },
}
</script>

<style>

</style>