<template>
  <div id="app">
    <section class="mt-2">
      <Header />
    </section>
    <section class="container">
      <router-view />
    </section>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'

export default {
  name: 'app',
  components: {
    Header
  }
}
</script>

<style lang='scss'>
html {
  background-color: #343a40 !important;
}

#app {
  font-family: "Muli", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-x: hidden;
  background-color: #343a40 !important;
  color: #ffffff;
}

#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
