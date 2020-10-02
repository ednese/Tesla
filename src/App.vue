<template>
  <div id="app">
    <Nav/>
    <Models/>
    <!-- <router-view/> -->
  </div>
</template>

<script>
import Nav from '@/components/Nav'
import Models from '@/components/Models'

export default {
  name: 'App',
  components: { Nav, Models }
}
</script>

<style>
body {
  margin: 0;
}
textarea:focus, input:focus, button {
  outline: none;
}
#app {
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700;800;900&family=Roboto:wght@300;400;500;700;900&display=swap');

  font-family: 'Montserrat', 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.underline {
    border-bottom: 1px solid currentColor;
    transition: all 0.3s ease-in-out;
  }
.underline:hover {
    border-bottom: 2px solid currentColor;
}
</style>
