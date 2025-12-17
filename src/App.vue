<script setup>
import Nav from './components/Nav.vue'
import Landing from './components/Landing.vue'
</script>

<template>
  <div class="app">
    <Nav />
    <Landing />
  </div>
</template>

<style>
/* GLOBAL RESET */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
}

/* APP CONTAINER */
.app {
  width: 100%;
  min-height: 100vh;
}

/* CONTAINER ZA SADRŽAJ (koristi za sekcije nakon landinga) */
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 24px;
}
</style>