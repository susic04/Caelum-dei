<script setup>
import { ref } from 'vue'

import Nav from './components/Nav.vue'
import Landing from './components/Landing.vue'
import Usluge from './components/usluge.vue'
import Usluga1 from './components/usluga_1.vue'
import Usluga2 from './components/usluga_2.vue'
import Usluga3 from './components/usluga_3.vue'
import Galerija from './components/galerija.vue'
import Kontakt from './components/kontakt.vue'

// GLAVNO STANJE
const prikaziKontakt = ref(false)
</script>

<template>
  <div class="app">
      <Nav />
      <Landing @naruci="prikaziKontakt = true" />
      <Usluge />
      <Usluga1 @naruci="prikaziKontakt = true" />
      <Usluga2 @naruci="prikaziKontakt = true" />
      <Usluga3 @naruci="prikaziKontakt = true" />
      <Galerija />
      <Kontakt />
    
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
  overflow-x: hidden;
}

/* APP CONTAINER */
.app {
  width: 100%;
  min-height: 100vh;
}

/* CONTAINER ZA SADRŽAJ */
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 24px;
}


html {
  scroll-behavior: smooth;
}

</style>
