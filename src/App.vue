<template>
  <Header/>
  <div class="space">1 блок</div>
  <div class="space">2 блок</div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header
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
}

.space {
  background-color: aliceblue;
  width: 100%;
  height: 100ch;
  z-index: -1000;
}
</style>
