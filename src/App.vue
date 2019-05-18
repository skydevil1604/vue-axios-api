<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
</script>

<style>
@font-face {
    font-family: 'SofiaPro';
    src: local('Sofia Pro Regular'), local('Sofia-Pro-Regular'),
        url('assets/fonts/SofiaProRegular.woff2') format('woff2'),
        url('assets/fonts/SofiaProRegular.woff') format('woff'),
        url('assets/fonts/SofiaProRegular.ttf') format('truetype');
    font-weight: 400;
    font-style: normal;
  };

#app {
  font-family: 'SofiaPro', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
}
</style>
