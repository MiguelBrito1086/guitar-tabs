<template>
  <div>
    <h1>Register</h1>
    <input type="email" name="email" placeholder="Email" v-model="email">
    <br>
    <input type="password" name="password" placeholder="Password" v-model="password">
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import authenticationService from '@/services/authenticationService';
export default {
  data () {
    return {
      email: "",
      password: ""
    }
  },
  methods: {
    async register() {
      await authenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log("Response: ", response.data);
    }
  }

}
</script>

<style>
</style>
