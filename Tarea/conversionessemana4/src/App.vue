<template>
  <div id="app">

    <h1>Cálculo de unidades</h1>

    <hr size="8" style="color:blue; background-color:blue">

    <br>

    <div class="row row-cols-1 row-cols-md-3 g-4">
      <div class="col">
        <time-conversion/>
      </div>
      <div class="col">
        <time-conversion/>
      </div>
      <div class="col">
        <time-conversion/>
      </div>
      <div class="col">
        <time-conversion/>
      </div>
      <div class="col">
        <time-conversion/>
      </div>
      <div class="col">
        <time-conversion/>
      </div>
    </div>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TimeConversion from './components/TimeConversion.vue'

export default {
  name: 'App',
  components: {
    TimeConversion
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
}
</style>
