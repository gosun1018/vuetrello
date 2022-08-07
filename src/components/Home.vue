<template>
  <div>
    <div>Home</div>
    <div>
      board list: 
      <div v-if="loading">loading...</div>
      <div v-else>
        Api result: {{apiRes}}
      </div>

      <div v-if="error">{{error}}</div>
      <router-link to="/board/1">board 1</router-link>
      <router-link to="/board/2">board 2</router-link>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      loading: false,
      apiRes: '',
      error: ''
    }
  },
  created() {
    this.fetchData()
  },
  methods: {
    fetchData() {
      this.loading = true
      axios.get('http://localhost:3000/health')
        .then(res => {
          this.apiRes = res.data
        })
        .catch(res => {
          this.error = res.response.data
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