<template>
<div id="app">

<UserProfile/>
</div>
</template>

<script>

import UserProfile from "./components/userProfile"

export default {
name: 'App',
components: {
  UserProfile
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
  display: flexbox;
  flex-direction: column;
}
</style>
