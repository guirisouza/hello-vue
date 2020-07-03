<template>
  <div id="app">
      <JobsOverview/>
  </div>
</template>

<script>
import JobsOverview from './components/JobsOverview.vue'

export default {
  name: 'App',
  components: {
    JobsOverview
  }
}
</script>

<style>
#app {
  font-family: 'Mukta', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
