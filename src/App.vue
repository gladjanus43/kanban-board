<template>
  <div id="app">
    <Dashboard/>
  </div>
</template>

<script>
import Dashboard from './components/Dashboard'

export default {
  name: "app",
  components: {
    Dashboard
  },
  data() {
    return {

    }
  }
}
</script>

<style>
* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}

h1, h2, h3{
  font-family: 'Ramabhadra', sans-serif;
}

p{
  font-family: 'Helvetica', sans-serif;
}
</style>
