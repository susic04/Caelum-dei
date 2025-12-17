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
  const slides = document.querySelectorAll('.slide')

  const updateScale = () => {
    const center = window.innerWidth / 2

    slides.forEach(slide => {
      const rect = slide.getBoundingClientRect()
      const slideCenter = rect.left + rect.width / 2
      const distance = Math.abs(center - slideCenter)

      const scale = Math.max(0.65, 1.15 - distance / 700)
      slide.style.transform = `scale(${scale})`
    })

    rafId = requestAnimationFrame(updateScale)
  }

  updateScale()
})

onUnmounted(() => {
  cancelAnimationFrame(rafId)
})
</script>



<template>
  <section id="usluge" class="usluge">
    <div class="slider">
      <div class="track">
        <img
          v-for="(slika, i) in slike"
          :key="i"
          :src="slika"
          class="slide"
          :alt="`Projekt ${i + 1}`"
        />

        <!-- DUPLIKAT ZA BESKONAČNI LOOP -->
        <img
          v-for="(slika, i) in slike"
          :key="'dup-' + i"
          :src="slika"
          class="slide"
        />
      </div>
    </div>
  </section>
</template>
<style scoed>
/* SEKCIJA */
.usluge {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* VIDLJIVI PROZOR */
.slider {
  width: 80vw;
  overflow: hidden;
}

/* TRAKA KOJA SE MIČE */
.track {
  display: flex;
  gap: 160px;                 /* ⬅️ nema gužve */
  animation: move 45s linear infinite;
}

/* SLIKE */
.slide {
  width: 220px;
  height: auto;
  flex-shrink: 0;

  transform: scale(0.7);
  transition: transform 0.2s ease-out;
  will-change: transform;
}

/* ANIMACIJA KRETANJA */
@keyframes move {
  from {
    transform: translateX(-50%);
  }
  to {
    transform: translateX(0);
  }
}
</style>
