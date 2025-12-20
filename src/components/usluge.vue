<script setup>
import { onMounted, onUnmounted } from 'vue'

import slika_1 from '../assets/slika_1.jpg'
import slika_2 from '../assets/slika_2.jpg'
import slika_3 from '../assets/slika_3.jpg'
import slika_4 from '../assets/slika_4.jpg'
import slika_5 from '../assets/slika_5.jpg'
import slika_6 from '../assets/slika_6.jpg'

const slike = [slika_1, slika_2, slika_3, slika_4, slika_5, slika_6]

let rafId

onMounted(() => {
  // nema JS grešaka
})

onUnmounted(() => {
  cancelAnimationFrame(rafId)
})
</script>

<template>
  <section id="usluge" class="usluge">
    <div class="slider">
      <div class="track">

        <!-- PRVI SET -->
        <div
          v-for="(slika, i) in slike"
          :key="i"
          class="slide-wrapper"
        >
          <img :src="slika" class="slide" :alt="`Projekt ${i + 1}`" />

          <a href="#kontakt" class="overlay">
            Naruči
          </a>
        </div>

        <!-- DUPLIKAT (za beskonačni scroll) -->
        <div
          v-for="(slika, i) in slike"
          :key="'dup-' + i"
          class="slide-wrapper"
        >
          <img :src="slika" class="slide" />
          <a href="#kontakt" class="overlay">
            Naruči
          </a>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.usluge {
  height: 50vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem 0;
}

.slider {
  width: 100vw;
  overflow: hidden;
}

.track {
  display: flex;
  gap: 60px;
  animation: move 15s linear infinite;
}

/* PAUZA NA HOVER */
.slider:hover .track {
  animation-play-state: paused;
}

/* WRAPPER */
.slide-wrapper {
  position: relative;
}

/* SLIKA */
.slide {
  width: 220px;
  height: 240px;          /* 👈 SVE ISTE VISINE */
  object-fit: cover;     /* 👈 crop bez deformacije */
  display: block;
  flex-shrink: 0;
}

/* OVERLAY */
.overlay {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.55);
  color: white;
  font-family: 'Georgia', serif;
  font-size: 1.2rem;
  font-weight: 500;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  opacity: 0;
  transition: opacity 0.3s ease;
}

/* HOVER EFEKTI */
.slide-wrapper:hover .overlay {
  opacity: 1;
}


/* ANIMACIJA */
@keyframes move {
  from {
    transform: translateX(-50%);
  }
  to {
    transform: translateX(0);
  }
}

/* TABLET */
@media (max-width: 1024px) {
  .slide {
    width: 200px;
    height: 220px;
  }

  .track {
    gap: 120px;
  }
}

/* MOBILE */
@media (max-width: 768px) {
  .slide {
    width: 170px;
    height: 190px;
  }
  .track {
    gap: 80px;
    animation: move 20s linear infinite;
  }
}

@media (max-width: 480px) {
  .slide {
    width: 140px;
    height: 160px;
  }
  .track {
    gap: 60px;
    animation: move 25s linear infinite;
  }
}
</style>
