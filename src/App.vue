<script setup>
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <div class="card bg-base-100 w-96 shadow-sm">
    <HelloWorld></HelloWorld>
    <button class="btn btn-accent px-5 py-1">hey</button>
  </div>
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
