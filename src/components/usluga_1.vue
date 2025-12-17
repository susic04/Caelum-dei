<script setup>
    import { ref, onMounted, onUnmounted } from 'vue'
    import slika_6 from '../assets/slika_6.jpg'
</script>

<template>
    <section id="usluga_1" class="usluga_1">
        <div class="okvir">
            <img :src="slika_6" class="slika_6"></img>
            <div class="slika_6_opis">
                <div class="opis">
                    <h1 class="naslov">Zahvalnice</h1>
                    <p class="tekst">
                        Svaki komad nastaje ručno,<br>
                        s pažnjom i molitvom.<br>
                        Drvo se reže i obrađuje s ljubavlju,<br>
                        perlice se pažljivo nižu, a svaka kartica<br>
                        slaže se korak po korak 
                    </p>
                </div>
                <button class="dugme">Naruči</button>
            </div>
        </div>
    </section>
</template>

<style scoped>
    .usluga_1{
        min-height: 100vh;
        background-color: white;
        min-width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .okvir{
        display: flex;
        height: auto;
        width: 75vw;
        max-width: 1200px;
        overflow: hidden;
    }
    .slika_6{
        height: 100%;
        width: 50%;
        object-fit: cover;
    }
    .slika_6_opis{
        flex-direction: column;
        display: flex;
        width: 50%;
        background: linear-gradient(135deg, #f5f7fa 0%, #e8eef5 50%, #d4dce8 100%);
        justify-content: center;
        padding: 4rem 3rem;
    }
    .opis{
        font-weight: 100;
        text-align: left;
        margin-bottom: 2.5rem;
        width: 100%;
    }
    .naslov{
        font-family: 'Georgia', serif;
        font-size: 2.5rem;
        font-weight: 500;
        margin-bottom: 1.5rem;
        line-height: 1.2;
        color: #2c3e50;
        margin-left: 2rem;
    }
    .tekst{
        font-size: 1.1rem;
        font-family: 'Georgia', serif;
        line-height: 1.8;
        color: #555;
        margin-left: 2rem;
    }
    .dugme{
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
        margin-left: 2rem;
    }
    .dugme:hover{
        background-color: #a93226;
        transform: translateY(-2px);
        box-shadow: 0 6px 20px rgba(192, 57, 43, 0.4);
    }
    .dugme:active{
        transform: translateY(0);
    }
</style>