<script setup>
defineProps({
  title: String,
  text: String,
  image: String,
  isEven: Boolean // Ako je true, slika ide desno (kao u tvojoj usluga_2)
})
</script>

<template>
  <section :class="['usluga-section', { 'white-bg': isEven, 'gradient-bg': !isEven }]">
    <div class="okvir" :class="{ 'reverse-layout': isEven }">
      
      <img :src="image" class="slika-usluge" :alt="title" />
      
      <div class="opis-kontejner" :class="{ 'gradient-bg': isEven, 'white-bg': !isEven }">
        <div class="opis-tekst">
          <h1 class="naslov">{{ title }}</h1>
          <p class="tekst" v-html="text"></p>
        </div>
        <button class="dugme">Naruči</button>
      </div>

    </div>
  </section>
</template>

<style scoped>
.usluga-section {
  min-height: 100vh;
  min-width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem 0;
}

/* Pozadine sekcija */
.gradient-bg { background: linear-gradient(135deg, #f5f7fa 0%, #e8eef5 50%, #d4dce8 100%); }
.white-bg { background-color: white; }

.okvir {
  display: flex;
  height: 60vh;
  width: 75vw;
  max-width: 1200px;
  overflow: hidden;
  border-radius: 20px; /* Malo moderniji radius */
  box-shadow: 0 10px 30px rgba(0,0,0,0.08);
}

.reverse-layout { flex-direction: row-reverse; }

.slika-usluge {
  height: 100%; /* Ispravljeno na 100% da popuni okvir */
  width: 50%;
  object-fit: cover;
}

.opis-kontejner {
  flex-direction: column;
  display: flex;
  width: 50%;
  justify-content: center;
  padding: 4rem 3rem;
}

.opis-tekst {
  text-align: left;
  margin-bottom: 2.5rem;
}

.naslov {
  font-family: 'Georgia', serif;
  font-size: 2.5rem;
  font-weight: 500;
  margin-bottom: 1.5rem;
  color: #2c3e50;
}

.tekst {
  font-size: 1.1rem;
  line-height: 1.8;
  color: #555;
}

.dugme {
  background-color: #c0392b;
  color: white;
  font-size: 1.1rem;
  padding: 0.9rem 3rem;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: all 0.3s ease;
  align-self: flex-start;
}

.dugme:hover {
  background-color: #a93226;
  transform: translateY(-2px);
}

/* RESPONSIVE - Zadržana tvoja logika */
@media (max-width: 768px) {
  .okvir { flex-direction: column; height: auto; width: 90vw; }
  .reverse-layout { flex-direction: column; } /* Na mobitelu slika uvijek gore */
  .slika-usluge { width: 100%; height: 300px; }
  .opis-kontejner { width: 100%; padding: 2.5rem 2rem; text-align: center; }
  .naslov, .tekst { text-align: center; }
  .dugme { align-self: center; }
  .slika-usluge { order: -1; } /* Osigurava da je slika uvijek iznad teksta */
}
</style>