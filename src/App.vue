<template>
  <div id="app">
    <TopNavbar></TopNavbar>
    <router-view/>
  </div>
</template>

<script>
import TopNavbar from '@/components/TopNavbar'

export default {
  name: 'App',
  components: {
    TopNavbar
  }
}
</script>

<style>
@import url(./assets/css/normalize.css);
@import url('https://fonts.googleapis.com/css?family=Noto+Sans+TC:400&display=swap&subset=chinese-traditional');
html {
  top: 0;
}
#app {
  font-family: 'Noto Sans TC', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  padding-top: 56px;
  background-color: #2f4353;
  background-image: linear-gradient(315deg, #d2ccc4 0%, #2f4353 74%);
}
</style>
