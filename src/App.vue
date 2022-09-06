<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import { onCreated, onMounted, onUnmounted, ref } from 'vue';

let state = ref('Not Initialized');
let x = ref(0);
let y = ref(0);

onMounted(() => {
  state.value = 'Mounted';
  window.addEventListener('mousemove', (event: MouseEvent) => {
    x.value = event.screenX;
    y.value = event.screenY;
  });
});

onUnmounted(() => {
  state = 'Unmounting';
  window.removeEventListener('mousemove');
});
</script>

<template>
  <div>
    {{ state }}
  </div>
  <div>X: {{ x }}</div>
  <div>Y: {{ y }}</div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
