<script setup>
import header_desktop from './components/header_deaktop.vue';
import header_mobile from './components/header_mobile.vue';
import banner from './components/banner.vue';
import index_content from './components/index_content.vue';
import footer_vue from './components/footer.vue';
</script>

<template>
  <div id="view" class="container-fluid p-0">
    <header_desktop class="header_desktop"/>
    <header_mobile />
    <div id="wrap">
      <banner v-if="true"/>
      <index_content />
      <footer_vue />
    </div>
  </div>
  
</template>

<style scoped lang="scss">
#view {
  display: flex;
  flex-direction: row;
}
.header_desktop {
  position: sticky;
  top: 0;
}
#wrap {
  flex-basis: 100%;
}
</style>
