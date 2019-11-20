<template>
  <div id="app">
    <Nav />
    <Dash />
    <Calendar />
    <Footer />
  </div>
</template>

<script>
import Nav from './components/Nav'
import Dash from './components/Dash'
import Calendar from './components/Calendar'
import Footer from './components/Footer'

export default {
  name: 'app',
  components: {
    Nav,
    Dash,
    Calendar,
    Footer
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100vw;
  height: 100vh;
}

</style>
