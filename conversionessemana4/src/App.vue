<template >
  <div id="app" :style="{'background-image':'url(https://images.pexels.com/photos/6863515/pexels-photo-6863515.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940)', 'background-size':'1200px 720px'}">
    <div class="fixed-top p-3 mb-2 text-white" style="background-color:indigo; margin-bottom">
      <h1>Cálculo de unidades</h1>
    </div>
    <br>
    <br>
    <center>
      <div class="row row-cols-1 row-cols-md-3 g-4">     <!-- div que contiene los componentes en columnas -->
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
    </center>
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
