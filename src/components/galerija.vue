<script setup>
    import { ref, onMounted } from 'vue'
    onMounted(() => {
        window.addEventListener('keydown', e => {
            if (e.key === 'Escape') aktivnaSlika.value = null
        })
    })
    import slika_1 from '../assets/slika_1.jpg'
    import slika_2 from '../assets/slika_2.jpg'
    import slika_3 from '../assets/slika_3.jpg'
    import slika_4 from '../assets/slika_4.jpg'
    import slika_5 from '../assets/slika_5.jpg'
    import slika_6 from '../assets/slika_6.jpg'
    import slika_7 from '../assets/slika_7.jpeg'
    import slika_8 from '../assets/slika_8.jpeg';
    const slike = [slika_1, slika_2, slika_3, slika_4, slika_5, slika_6, slika_7, slika_8];
    const aktivnaSlika = ref(null)
</script>

<template>
    <div class="container">
        <div class="div-naslov">
            <h1 class="naslov">Galerija</h1>
            
        </div>
        <div class="grid">
            <img
                v-for="(slika, i) in slike"
                :key="i"
                :src="slika"
                class="slika"
                @click="aktivnaSlika = slika"
            />
        </div>
        <div
            v-if="aktivnaSlika"
            class="lightbox"
            @click.self="aktivnaSlika = null"
            >
            <button class="close" @click="aktivnaSlika = null">×</button>

            <img :src="aktivnaSlika" class="lightbox-img" />
        </div>
    </div>
</template>

<style scoped>
    .container {
        height: 100vh;
        width: 100vw;
        background-color: white;
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center; /* 👈 OVO */
    }
    .div-naslov {
        width: 100%;
        height: 10%;
        text-align: center;
        margin-bottom: 4rem;
    }
    .naslov{
        font-family: 'Georgia', serif;
        font-size: 2.5rem;
        font-weight: 500;
        line-height: 1.2;
        color: #2c3e50;
    }
    .grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 1rem;
        width: 75vw;
        justify-items: center; /* 👈 OVO */
    }

    .slika {
        width: 100%;
        max-width: 220px;
        height: 200px;
        object-fit: cover;
        
    }
    .slika,
    .slide,
    .slide-wrapper {
        cursor: pointer;
    }

    .lightbox {
        position: fixed;
        inset: 0;
        background: rgba(0, 0, 0, 0.85);
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 9999;
    }

    .lightbox-img {
        max-width: 90vw;
        max-height: 90vh;
        object-fit: contain;
        border-radius: 6px;
    }

    .close {
        position: absolute;
        top: 20px;
        right: 25px;
        background: none;
        border: none;
        color: white;
        font-size: 36px;
        cursor: pointer;
    }
    .lightbox-img {
        animation: zoomIn 0.3s ease;
        }

        @keyframes zoomIn {
        from {
            transform: scale(0.85);
            opacity: 0;
        }
        to {
            transform: scale(1);
            opacity: 1;
        }
    }

</style>