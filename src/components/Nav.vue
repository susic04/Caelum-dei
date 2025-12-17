<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const visible = ref(false)
const scrolled = ref(false)

onMounted(() => {
  setTimeout(() => {
    visible.value = true
  }, 500)
  
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

const handleScroll = () => {
  scrolled.value = window.scrollY > 50
}
</script>

<template>
  <nav class="nav" :class="{ visible, scrolled }">
    <ul class="menu">
      <li>
        <a href="#onama" class="menu-item">
          <i class="fa-solid fa-user" aria-hidden="true"></i>
          <span class="tooltip">O Nama</span>
        </a>
      </li>
      <li>
        <a href="#" class="menu-item home">
          <i class="fa-solid fa-house" aria-hidden="true"></i>
          <span class="tooltip">Početna</span>
        </a>
      </li>
      <li>
        <a href="#usluge" class="menu-item">
          <i class="fa-solid fa-pen-nib" aria-hidden="true"></i>
          <span class="tooltip">Usluge</span>
        </a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.nav {
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%) translateY(-100px);
  z-index: 1000;
  
  background: rgba(255, 255, 255, 0.85);
  backdrop-filter: blur(10px);
  border-radius: 50px;
  padding: 12px 24px;
  border: 1px solid rgba(255, 255, 255, 0.3);
  
  opacity: 0;
  transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
  
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
}

.nav.visible {
  transform: translateX(-50%) translateY(0);
  opacity: 1;
}

.nav.scrolled {
  background: rgba(255, 255, 255, 0.98);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.12);
}

.menu {
  display: flex;
  gap: 0.5rem;
  list-style: none;
  margin: 0;
  padding: 0;
  align-items: center;
  justify-content: center;
}

.menu li {
  position: relative;
}

.menu-item {
  display: flex;
  align-items: center;
  justify-content: center;
  
  width: 48px;
  height: 48px;
  
  text-decoration: none;
  color: #2c3e50;
  
  border-radius: 50%;
  background: transparent;
  
  transition: all 0.3s ease;
  position: relative;
}

.menu-item:hover {
  background: rgba(44, 62, 80, 0.08);
  transform: translateY(-2px);
}

.menu-item.home {
  background: rgba(44, 62, 80, 0.08);
}

.menu-item.home:hover {
  background: rgba(44, 62, 80, 0.15);
}

.menu-item i {
  font-size: 18px;
  margin: 0;
  padding: 0;
  width: auto;
  height: auto;
  transition: transform 0.3s ease;
}

.menu-item:hover i {
  transform: scale(1.15);
}

.tooltip {
  position: absolute;
  bottom: -38px;
  left: 50%;
  transform: translateX(-50%) scale(0.8);
  
  background: rgba(44, 62, 80, 0.95);
  color: white;
  padding: 8px 14px;
  border-radius: 8px;
  font-size: 13px;
  white-space: nowrap;
  font-weight: 500;
  
  opacity: 0;
  pointer-events: none;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.tooltip::before {
  content: '';
  position: absolute;
  top: -5px;
  left: 50%;
  transform: translateX(-50%);
  
  width: 0;
  height: 0;
  border-left: 6px solid transparent;
  border-right: 6px solid transparent;
  border-bottom: 6px solid rgba(44, 62, 80, 0.95);
}

.menu-item:hover .tooltip {
  opacity: 1;
  transform: translateX(-50%) scale(1);
}

/* TABLET */
@media (max-width: 1024px) {
  .nav {
    padding: 10px 20px;
  }

  .menu {
    gap: 0.4rem;
  }

  .menu-item {
    width: 44px;
    height: 44px;
  }

  .menu-item i {
    font-size: 17px;
  }

  .tooltip {
    font-size: 12px;
    padding: 7px 12px;
  }
}

/* MOBILE */
@media (max-width: 768px) {
  .nav {
    top: auto;
    bottom: 20px;
    padding: 8px 16px;
  }

  .nav.visible {
    transform: translateX(-50%) translateY(0);
  }
  
  .menu {
    gap: 0.3rem;
  }
  
  .menu-item {
    width: 42px;
    height: 42px;
  }
  
  .menu-item i {
    font-size: 16px;
  }
  
  .tooltip {
    display: none;
  }

  .menu-item:hover {
    transform: none;
  }
}

@media (max-width: 480px) {
  .nav {
    bottom: 15px;
    padding: 6px 12px;
  }

  .menu {
    gap: 0.2rem;
  }

  .menu-item {
    width: 38px;
    height: 38px;
  }

  .menu-item i {
    font-size: 15px;
  }
}
</style>