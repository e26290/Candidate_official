<script setup>
import header_desktop from './components/header_deaktop.vue';
import banner from './components/banner.vue';
</script>

<template>
  <div class="view container-fluid p-0">
    <header_desktop />
    <banner />
  </div>
  

</template>

<style scoped lang="scss">
.view {
  display: flex;
  flex-direction: row;
}
</style>
