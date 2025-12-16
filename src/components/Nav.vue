<script setup>
import { ref, onMounted } from 'vue'

const visible = ref(false)

onMounted(() => {
  // mala odgoda da browser vidi početno stanje
  setTimeout(() => {
    visible.value = true
  }, 50)
})
</script>


<template>
  <nav class="nav" :class="{ visible }">
    <ul class="menu">
      <li>
        <a href="#onama" class="menu-item">
          <i class="fa-solid fa-user" aria-hidden="true"></i>
          <span></span>
      
        </a>
      </li>
      <li>
        <a href="#">
          <i class="fa-solid fa-house" aria-hidden="true"></i>
          <span></span>
    
        </a>
      </li>
      <li>
        <a href="#usluge">
          <i class="fa-solid fa-pen-nib" aria-hidden="true"></i>
          <span></span>
        </a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>

.nav {
  position: sticky;
  top: 0;
  z-index: 1000;
  background-color: white;  
}
.menu {
  display: flex;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
  align-items: center;
  justify-content: center;
}
.menu i{
  margin-top: 15px;
  padding: 0;
  width: 30px;
  height: 30px;
  align-items: center;
  justify-content: center;
  border: none;
}
.menu a {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
  color: inherit;
  border: none;
  box-shadow: none;
}


.menu-item {
  width: 30px;
  height: 30px;

  display: flex;
  flex-direction: column;   
  justify-content: center;  
  align-items: center;      

  border: 1px solid #ccc;
}

.nav {
  opacity: 0;
  transform: translateY(-10px);
}

.nav.visible {
  opacity: 1;
  transform: translateY(0);
  transition: opacity 3s ease, transform 3s ease;
}
</style>