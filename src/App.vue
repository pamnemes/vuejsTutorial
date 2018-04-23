<template>
  <div id="app">
    <div class="container-fluid">
      <div class="row">
        <div class="col-12"> <Banner /></div>
      </div>
      <div class="row mt-3">
        <div class="col-4"><SideMenu /></div>
        <div class="col-8"><router-view /></div>
      </div>
    </div>
  </div>
</template>
<script>
import Banner from '@/components/Banner'
import SideMenu from '@/components/SideMenu'
export default {
  name: 'App',
  components: {
    Banner,
    SideMenu
  }
}
</script>

<style>
@import "bootstrap/dist/css/bootstrap.css";
@import "bootstrap-vue/dist/bootstrap-vue.css";
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 0px;
}
</style>
