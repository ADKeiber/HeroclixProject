<script setup lang="ts">
import { ref } from 'vue'
import Tabs from './Tabs.vue'


const tabs = ref<string[]>(['Connect', 'Create'])
const selectedTab = ref('Connect')

const ages = ref<string[]>(['Modern', 'Modern (\'22-\'24)', 'Modern (\'20-\'23)', 'Silver', 'Silver (Late 2024)', 'Silver (Early 2024)', 'Silver (2023)', 'Bronze', 'Golden'])
const formats = ref<string[]>(['Standard', 'Pulp', 'Theme', 'Highlander'])

const selectedAge = ref('')
const selectedFormat = ref('')
</script>

<template>
  <div class="box">
    <Tabs v-model:tabs="tabs" v-model:selected="selectedTab" ></Tabs>
    <div v-if="selectedTab === 'Create'">
      
      <div class="input">
        <label>User's Name: </label>
        <input placeholder="User's Name"/>
      </div>
  
      <div class="input">
        <label>Number of players: </label>
        <input placeholder="Number of Players"/>
      </div>

      <div class="input">
        <label>Point Limit: </label>
        <input placeholder="Point Limit"/>
      </div>

      <div class="input">
        <label>Format: </label>
        <select id="format" v-model="selectedFormat">
          <option v-for="format in formats" :key="format" :value="format">
            {{ format }}
          </option>
        </select>
      </div>
  
      <div class="input">
        <label>Age: </label>
        <select id="age" v-model="selectedAge">
          <option v-for="age in ages" :key="age" :value="age">
            {{ age }}
          </option>
        </select>
      </div>

      <button>Create Game</button>

    </div>
    <div v-if="selectedTab === 'Connect'">

      <div class="input">
        <label>User's Name: </label>
        <input placeholder="User's Name"/>
      </div>
  
      <div class="input">
        <label>Server ID: </label>
        <input placeholder="Server ID"/>
      </div>

      <button>Connect</button>

    </div>
  </div>
</template>

<style>
  .input {
    display:flex;
  }

  .box {
    max-width: 33vw;
    min-width: 250px;
    width: 100%;
    max-height: 33vh;
    min-height: 350px;
    background: lightgray;
    border-radius: 8px;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  }
</style>