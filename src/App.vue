<script setup>
import header_desktop from './components/header_deaktop.vue';
import banner from './components/banner.vue';
import footer_vue from './components/footer.vue';
</script>

<template>
  <div id="view" class="container-fluid p-0">
    <header_desktop class="header_desktop"/>
    <div id="wrap">
      <banner />
      <footer_vue />
    </div>
  </div>
  
</template>

<style scoped lang="scss">
#view {
  display: flex;
  flex-direction: row;
  height: 100vh;
}
.header_desktop {
  position: sticky;
}
#wrap {
  flex-basis: 100%;
  height: 100vh;
}
</style>
