<template>
  <v-layout column>
<v-flex xs6 offset-xs3>
  <div class="white elevation-2">
    <v-toolbar flat dense class="cyan" dark>
      <v-toolbar-title>
        Register
      </v-toolbar-title>
    </v-toolbar>
    <div class="pl-4 pr-4 pt-2 pb-2">
      <v-text-field
        label="Email"
        name="input-1"
        v-model="email"
      />
      <v-text-field
        label="Password"
        name="input-2"
        v-model="password"
      />

      <v-alert color="error" icon="warning" :value="error || false">
      {{ error }}
      </v-alert>
      <br>
      <v-btn class="cyan" dark
        @click="register">Register</v-btn>

    </div>


  </div>
</v-flex>
  </v-layout>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: '',
      error: null
    }
  },
  methods: {
    async register () {
      try {
        await AuthenticationService.register({
          email: this.email,
          password: this.password
        })
      } catch (error) {
        this.error = error.response.data.error
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
