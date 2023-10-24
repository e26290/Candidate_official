<script setup>
import header_desktop from './components/header_deaktop.vue';
import banner from './components/banner.vue';
</script>

<template>
  <!-- 這邊切錯了，header應該是要固定在左邊，可以sroll是右邊區塊 -->
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
