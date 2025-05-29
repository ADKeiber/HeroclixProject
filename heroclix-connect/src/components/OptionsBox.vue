<script setup lang="ts">
import { ref } from 'vue'
import Tabs from './Tabs.vue'


const tabs = ref<string[]>(['Create', 'Connect'])
const selectedTab = ref('Create')

</script>

<template>
  <div :style="{ width:'33vw'}">
    <Tabs v-model:tabs="tabs" v-model:selected="selectedTab" ></Tabs>
    <div>{{ selectedTab }}</div>
  </div>
</template>