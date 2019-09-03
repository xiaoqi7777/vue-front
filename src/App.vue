<template>
  <ul id="app">
    <li v-for="(user,index) in users" :key="index">
      {{user.name}}
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  name: 'app',
  data(){
    return{
      users:[]
    }
  },
  async  mounted(){
    let users = await axios.get('http://localhost:3000/api/users')
    this.users = users.data
  }
}
</script>

<style>

</style>
