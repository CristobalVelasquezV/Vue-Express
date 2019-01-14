<template>
  <div>
    <h1>Register</h1>

    <input type="email" name="email" placeholder="Email" v-model="email">
    <br>
    <input type="password" name="password" placeholder="Password" v-model="password">
    <br>
    <button @click="sendRegisterData">Register</button>

  </div>
</template>

<script>
import AuthenticationService from '@/services/authenticationService'
export default {
  data () {
    return {
      email: 'abc',
      password: '123'
    }
  },
  methods: {
    async sendRegisterData () {
      const response = await AuthenticationService.register({ email: this.email, password: this.password })
      console.log(response.data)
    }
  },
  watch: {
    email (value) {
      console.log('email value has changed', value)
    }
  }
}
</script>
