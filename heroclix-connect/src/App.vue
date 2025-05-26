<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="app-container">
    <RouterView />
  </div>
</template>

<style scoped>
  .app-container {
    height: 100vh;
    width: 100vw;
    display: flex;         /* Optional for layout */
    justify-content: center;
    align-items: center;
    background-image: linear-gradient(to right, rgb(242, 242, 242), rgb(217, 217, 217));
  }
</style>
