<script setup lang="ts">
const props = defineProps(['tabs', 'selected'])
const emit = defineEmits(['update:selected'])

function switchTab(tabName: string){
  emit('update:selected', tabName)
}

</script>

<template>
  <div v-for="(tabName, index) in tabs" :key="index" @click="switchTab(tabName)">
    {{ tabName }}
  </div>
</template>
