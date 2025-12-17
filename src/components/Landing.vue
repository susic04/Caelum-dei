<script setup>
import { onMounted, ref } from 'vue'
import logo from '../assets/logo.png'

const active = ref(false)

onMounted(() => {
  setTimeout(() => {
    active.value = true
  }, 100)
})
</script>

<template>
  <section class="landing" :class="{ active }">
    <div class="landing-content">
      
      <div class="logo-container">
        <img
          :src="logo"
          alt="Caelum Dei logo"
          class="logo-landing"
        />
      </div>

      <div class="tekst-landing">
        <h1 class="naslov">Caelum Dei</h1>
        <h3 class="podnaslov">OD NITI DO NEBA</h3>
      </div>

    </div>
  </section>
</template>

<style scoped>
.landing {
  position: relative;
  height: 100vh;
  width: 100vw;
  margin-left: calc(-50vw + 50%);
  background: linear-gradient(135deg, #f5f7fa 0%, #e8eef5 50%, #d4dce8 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.landing-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  max-width: 90%;
  transform: translateY(20px);
  opacity: 0;
  transition: all 1.2s cubic-bezier(0.4, 0, 0.2, 1);
}

.active .landing-content {
  transform: translateY(0);
  opacity: 1;
}

.logo-container {
  transform: scale(0.8);
  opacity: 0;
  transition: all 1s ease 0.3s;
}

.active .logo-container {
  transform: scale(1);
  opacity: 1;
}

.logo-landing {
  height: 45vh;
  width: auto;
  max-width: 80vw;
  filter: drop-shadow(0 15px 40px rgba(0, 0, 0, 0.12));
  transition: transform 0.4s ease;
}

.logo-landing:hover {
  transform: scale(1.05);
}

.tekst-landing {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  transform: translateY(30px);
  opacity: 0;
  transition: all 1s ease 0.6s;
}

.active .tekst-landing {
  transform: translateY(0);
  opacity: 1;
}

.naslov {
  font-family: 'Dancing Script', cursive;
  font-size: 5rem;
  font-weight: 400;
  margin: 0;
  color: #2c3e50;
  line-height: 1.2;
  letter-spacing: 2px;
}

.podnaslov {
  font-weight: 300;
  font-size: 1.8rem;
  margin: 1rem 0 0 0;
  color: #546e7a;
  letter-spacing: 4px;
  text-transform: uppercase;
  font-family: 'Georgia', serif;
}

/* TABLET */
@media (max-width: 1024px) {
  .landing-content {
    gap: 2.5rem;
  }

  .logo-landing {
    height: 35vh;
  }
  
  .naslov {
    font-size: 4rem;
  }
  
  .podnaslov {
    font-size: 1.5rem;
    letter-spacing: 3px;
  }
}

/* MOBILE */
@media (max-width: 768px) {
  .landing-content {
    gap: 2rem;
  }

  .logo-landing {
    height: 28vh;
  }
  
  .naslov {
    font-size: 3rem;
  }
  
  .podnaslov {
    font-size: 1.1rem;
    letter-spacing: 3px;
  }
}

@media (max-width: 480px) {
  .landing {
    padding: 0 1rem;
  }

  .landing-content {
    gap: 1.5rem;
  }

  .logo-landing {
    height: 22vh;
  }
  
  .naslov {
    font-size: 2.2rem;
    letter-spacing: 1px;
  }
  
  .podnaslov {
    font-size: 0.9rem;
    letter-spacing: 2px;
  }
}
</style>