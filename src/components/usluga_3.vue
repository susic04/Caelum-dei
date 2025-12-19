<script setup>
    import slika_8 from '../assets/slika_8.jpeg'
    import { ref } from 'vue'
</script>

<template>
    <section id="usluga_3" class="usluga_3">
        <div class="okvir">
            <img :src="slika_8" class="slika_8" alt="Privjesci" />
            <div class="slika_8_opis">
                <div class="opis">
                <h1 class="naslov">Privjesci za ključeve</h1>
                <p class="tekst">
                    Kuglice se nižu s pažnjom,<br>
                    svaka molitva utkana u rad.<br>
                    Male duhovne pratioce stvaram ručno,<br>
                    spajajući vjeru i svakodnevicu,<br>
                    privjesci koji nose mir i zaštitu
                </p>
                </div>
                <button class="dugme">Naruči</button>
            </div>
        </div>
    </section>
</template>


<style scoped>
.usluga_3 {
  min-height: 100vh;
  background: linear-gradient(135deg, #f5f7fa 0%, #e8eef5 50%, #d4dce8 100%);
  min-width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem 0;
}

.okvir {
  display: flex;
  height: 60vh;
  width: 75vw;
  max-width: 1200px;
  overflow: hidden;
  border-radius: 2%;
}

.slika_8 {
  height: 80%;
  width: 50%;
  object-fit: cover;
}

.slika_8_opis {
  flex-direction: column;
  display: flex;
  width: 50%;
  background-color: white;
  justify-content: center;
  padding: 4rem 3rem;
}

.opis {
  font-weight: 100;
  text-align: left;
  margin-bottom: 2.5rem;
  width: 100%;
}

.naslov {
  font-family: 'Georgia', serif;
  font-size: 2.5rem;
  font-weight: 500;
  margin-bottom: 1.5rem;
  line-height: 1.2;
  color: #2c3e50;
}

.tekst {
  font-size: 1.1rem;
  font-family: 'Georgia', serif;
  line-height: 1.8;
  color: #555;
}

.dugme {
  background-color: #c0392b;
  color: white;
  font-family: 'Georgia', serif;
  font-size: 1.1rem;
  font-weight: 500;
  padding: 0.9rem 3rem;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(192, 57, 43, 0.3);
  align-self: flex-start;
}

.dugme:hover {
  background-color: #a93226;
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(192, 57, 43, 0.4);
}

.dugme:active {
  transform: translateY(0);
}

/* TABLET */
@media (max-width: 1024px) {
  .okvir {
    width: 85vw;
    height: auto;
  }

  .slika_8 {
    height: 100%;
  }

  .slika_8_opis {
    padding: 3rem 2.5rem;
  }

  .naslov {
    font-size: 2.2rem;
  }

  .tekst {
    font-size: 1rem;
  }

  .dugme {
    padding: 0.8rem 2.5rem;
    font-size: 1rem;
  }
}

/* MOBILE */
@media (max-width: 768px) {
  .usluga_3 {
    padding: 1rem;
  }

  .okvir {
    flex-direction: column;
    width: 90vw;
    height: auto;
  }

  .slika_8 {
    width: 100%;
    height: 300px;
  }

  .slika_8_opis {
    width: 100%;
    padding: 2.5rem 2rem;
  }

  .opis {
    margin-bottom: 2rem;
  }

  .naslov {
    font-size: 2rem;
    text-align: center;
  }

  .tekst {
    font-size: 0.95rem;
    text-align: center;
  }

  .dugme {
    align-self: center;
    padding: 0.8rem 2.5rem;
  }
}

@media (max-width: 480px) {
  .okvir {
    width: 95vw;
  }

  .slika_8 {
    height: 250px;
  }

  .slika_8_opis {
    padding: 2rem 1.5rem;
  }

  .naslov {
    font-size: 1.8rem;
  }

  .tekst {
    font-size: 0.9rem;
    line-height: 1.6;
  }

  .tekst br {
    display: none;
  }

  .dugme {
    padding: 0.75rem 2rem;
    font-size: 0.95rem;
  }
}
</style>