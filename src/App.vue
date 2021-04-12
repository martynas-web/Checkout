<template>
  <div id="app">
<TopBar />
<Header />
    <router-view/>
  </div>
</template>

<script>
import Header from "./components/layout/Header"
import TopBar from "./components/layout/TopBar"
export default {
name:"app",
components: {
  Header,
  TopBar
}
}
</script>


<style>
#app {
  @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  letter-spacing: 1px;
}
</style>
