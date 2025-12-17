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

<style scoped>
.usluge {
  min-height: 50vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem 0;
}

.slider {
  width: 80vw;
  overflow: hidden;
  border-radius: 10%;
}

.track {
  display: flex;
  gap: 160px;
  animation: move 15s linear infinite;
}

.slide {
  width: 220px;
  height: auto;
  flex-shrink: 0;
  border-radius: 5%;
  transform: scale(0.7);
  transition: transform 0.2s ease-out;
  will-change: transform;
}

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
  .slider {
    width: 85vw;
  }

  .track {
    gap: 120px;
  }

  .slide {
    width: 180px;
  }
}

/* MOBILE */
@media (max-width: 768px) {
  .usluge {
    min-height: 40vh;
  }

  .slider {
    width: 90vw;
  }

  .track {
    gap: 80px;
    animation: move 20s linear infinite;
  }

  .slide {
    width: 150px;
  }
}

@media (max-width: 480px) {
  .usluge {
    min-height: 35vh;
  }

  .slider {
    width: 95vw;
  }

  .track {
    gap: 60px;
    animation: move 25s linear infinite;
  }

  .slide {
    width: 120px;
  }
}
</style>