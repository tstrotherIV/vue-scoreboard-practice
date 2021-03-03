<template>
  <div id="app">
    <Scorboard />
  </div>
</template>

<script>
import Scorboard from "./components/scoreboad"


export default {
  components: {
    Scorboard,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  background-color: #2c3e50;
}
</style>
