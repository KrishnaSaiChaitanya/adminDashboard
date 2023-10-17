<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Layout from './components/Layout.vue';
import NavBar from './components/NavBar.vue';
import Sidebar from './components/Sidebar.vue'
</script>

<template>
  <!-- <NavBar /> -->
  <Layout />
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
