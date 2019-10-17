<template>
  <ul>
    <li v-for="(item,key) in users"
        :key="key">{{item.name}}</li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  name: 'app',
  data() {
    return {
      users: []
    }
  },
  mounted() {
    axios.get('http://localhost:3009/api/users').then(res => {
      this.users = res.data
    })
  },
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
