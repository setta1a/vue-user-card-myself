<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <UserCard :login="login" :avatar="avatar" :firstname="firstName" :lastname="lastName" :phone="phone" :email="email" :adress="adress" />
</template>

<script>
import UserCard from './components/userCard.vue'

export default {
  name: 'App',
  components: {
    UserCard,
  },
  data(){
      return {
        avatar: '',
        login: '',
        firstName: '',
        lastName: '',
        adress: '',
        phone: '',
        email: ''
      }
    },
    methods(){
      getUserData = function(){
        this.axios.get("https://randomuser.me/api/").then((response) => {
            let info = response.data.results[0]
            console.log(info)
            this.adress = info.location.city + "," + info.location.street.name;
            this.avatar = info.picture.medium;
            this.nickname = info.login.username;
            this.email = info.email;
            this.phone = info.phone;
            this.firstName = info.name.first;
            this.lastName = info.name.last;
        })
      }
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
