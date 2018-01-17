<template>
  <v-toolbar fixed class="cyan" dark>
    <v-toolbar-title class="mr-4">
      <router-link to="/" tag="span" class="home">TabTracker</router-link>
    </v-toolbar-title>
    <v-toolbar-items>
      <v-btn flat dark router to="/">Browse</v-btn>
    </v-toolbar-items>
    <v-spacer></v-spacer>
    <v-toolbar-items>
      <v-btn flat dark router to="/login">
        Login
      </v-btn>
      <v-btn flat dark router to="/register">
        Sign Up
      </v-btn>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>
  export default {
    name: 'header'
  }
</script>

<style scoped>
.home {
  cursor: pointer;
}
.home:hover {
   color: aquamarine;
  }
</style>
