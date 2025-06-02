<script setup lang="ts">
  import { ref } from 'vue'

  const props = defineProps(['tabs', 'selected'])
  const emit = defineEmits(['update:selected'])
  const divider = ref(props.tabs.length)
  var selectedTabIndex = 0
  function switchTab(tabName: string, tabIndex: number){
    selectedTabIndex = tabIndex
    emit('update:selected', tabName)
  }

</script>

<template>
  <div class="parent">
    <div class="child" :style="{width:`calc(100% / ${divider})`}" :class="selectedTabIndex == index? 'selectedTab' : 'unselectedTab' " v-for="(tabName, index) in tabs" :key="index" @click="switchTab(tabName, index)" >
      {{ tabName }}
    </div>
  </div>
  
</template>

<style>
  .parent {
    display: flex;
    border-bottom: 1px solid black;
  }

  .child {
    height: 30px;
    text-align: center;
  }

  .child + .child {
    border-left: 1px solid black;
  }

  .selectedTab {
    background: rgb(191, 191, 191);
  }

  .unselectedTab {
    background: lightgray;
  }

</style>