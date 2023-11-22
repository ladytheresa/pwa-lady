<script setup>
import HelloWorld from './components/HelloWorld.vue'
import ReloadPrompt from './components/ReloadPrompt.vue'
import fetch from './components/fetch.vue'
import crud from './components/crud.vue'
</script>

<template>
  <div>
    <h1>Ver 3.0</h1>
    <ReloadPrompt />
    <crud />
    <fetch />
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
