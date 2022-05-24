<script setup>
import ProgressPie from './ProgressPie.vue'
import { ref } from 'vue'

const pie0 = ref(10)
const pie1 = ref(25)
const pie2 = ref(90)
const pie3 = ref(55)
</script>

<template>
  <h2>Coral;</h2>
  <div style="display: flex; align-items: center">
    <ProgressPie
      color="Coral"
      :percentage="pie0"
    />
    <div>
      <button @click="pie0 = 0">0</button>
      <button @click="pie0 = 25">25</button>
      <button @click="pie0 = 50">50</button>
      <button @click="pie0 = 72">72</button>
      <button @click="pie0 = 100">100</button>
    </div>
  </div>

  <h2>DarkCyan; Round; No track</h2>
  <div style="display: flex; align-items: center">
    <ProgressPie
      color="DarkCyan"
      :track="false"
      :percentage="pie1"
      linecap="round"
    />
    <div>
      <button @click="pie1 = 0">0</button>
      <button @click="pie1 = 25">25</button>
      <button @click="pie1 = 50">50</button>
      <button @click="pie1 = 72">72</button>
      <button @click="pie1 = 100">100</button>
    </div>
  </div>

  <h2>DarkOrchid; width:15px</h2>
  <div style="display: flex; align-items: center">
    <ProgressPie
      color="DarkOrchid"
      width="15"
      :percentage="pie2"
    />
    <div>
      <button @click="pie2 = 0">0</button>
      <button @click="pie2 = 25">25</button>
      <button @click="pie2 = 50">50</button>
      <button @click="pie2 = 72">72</button>
      <button @click="pie2 = 100">100</button>
    </div>
  </div>

  <h2>GoldenRod; width: 5px</h2>
  <div style="display: flex; align-items: center">
    <ProgressPie
      color="GoldenRod"
      width="5"
      :percentage="pie3"
    />
    <div>
      <button @click="pie3 = 0">0</button>
      <button @click="pie3 = 25">25</button>
      <button @click="pie3 = 50">50</button>
      <button @click="pie3 = 72">72</button>
      <button @click="pie3 = 100">100</button>
    </div>
  </div>
</template>
