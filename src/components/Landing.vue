<script setup>
import { onMounted, ref } from 'vue'
import logo from '../assets/logo.png'

const active = ref(false)

onMounted(() => {
  requestAnimationFrame(() => {
    active.value = true
  })
})
</script>

<template>
  <section class="landing" :class="{ active }">

    <div class="tekst-landing">
      <h1 class="naslov">Caelum Dei</h1>
      <h3 class="podnaslov">OD NITI DO NEBA</h3>
      <p class="landing-paragraf">
        Dragi moji, s puno ljubavi i uzbuđenja želim vas uvesti u svijet mog malog kreativnog projekta.
      </p>
    </div>

    <img
      :src="logo"
      alt="Caelum Dei logo"
      class="logo-landing"
    />

  </section>
</template>

<style scoped>
/* LAYOUT */
.landing{
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
}

/* TEKST */
.naslov {
  font-family: 'Dancing Script', cursive;
  font-size: 5rem;
  font-weight: 200;
  margin: 0;
}

.podnaslov{
  font-weight: 200;
  font-size: 2rem;
  margin-top: 0;
  margin-bottom: 20%;
}

.landing-paragraf{
  margin-bottom: 20%;
}

/* LOGO */
.logo-landing{
  height: 70%;
  width: 40%;
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%);
  opacity: 0;
}

/* TEKST POČETNO */
.tekst-landing{
  position: absolute;
  top: 50%;
  left: 10%;
  transform: translate(-40px, -50%);
  opacity: 0;
}

/* === ANIMACIJE === */
.active .logo-landing{
  animation:
    logoAppear 1s ease forwards,
    logoMove 1.5s ease forwards;
  animation-delay:
    0.5s,
    2s;
}

.active .tekst-landing{
  animation: textReveal 1.5s ease forwards;
  animation-delay: 3.5s;
}

/* KEYFRAMES */
@keyframes logoAppear {
  to { opacity: 1; }
}

@keyframes logoMove {
  to {
    left: 75%;
    transform: translate(-50%, -50%);
  }
}

@keyframes textReveal {
  to {
    opacity: 1;
    transform: translate(0, -50%);
  }
}
</style>
