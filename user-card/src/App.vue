<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <UserCard :login="login" :avatar="avatar" :firstname="firstName" :lastname="lastName" :phone="phone" :email="email" :adress="adress" />
</template>

<script>
import UserCard from './components/userCard.vue'

export default {
  name: 'App',
  components: {
    UserCard
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
