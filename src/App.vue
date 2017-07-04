<template>
  <div id="app">
    <nav class="navbar navbar-default navbar-fixed-top">
      <router-link to="/hello" class="btn btn-default navbar-btn">To hello</router-link>
      <!-- <router-link to="detail" class="btn btn-default navbar-btn">To datail</router-link> -->
      <router-link to="/List" class="btn btn-default navbar-btn">To list</router-link>
    </nav>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

a,
a:hover,
a:active{
  color:#2c3e50
}
</style>
