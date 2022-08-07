<template>
  <div>
    <div>Home</div>
    <div>
      board list: 
      <div v-if="loading">loading...</div>
      <div v-else>
        <div v-for="b in boards" :key="b.id">
          {{b}}
        </div>
      </div>
      <router-link to="/board/1">board 1</router-link>
      <router-link to="/board/2">board 2</router-link>
    </div>
  </div>
</template>

<script>
import {board} from '../api'

export default {
  data() {
    return {
      loading: false,
      boards: []
    }
  },
  created() {
    this.fetchData()
  },
  methods: {
    fetchData() {
      this.loading = true
      board.fetch()
        .then(data => {
          this.boards = data
        })
        .finally(() => {
          this.loading = false
        })
    }
  },
}
</script>

<style>
  
</style>