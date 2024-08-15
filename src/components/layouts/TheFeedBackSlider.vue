<script setup>
import ArrowForwardIcon from '../icons/ArrowForwardIcon.vue';
import { ref } from 'vue';

const index = ref(0);
const slides = ref([
    {
        image: '/src/assets/images/face.jpg',
        feedback: `"Be genuine in your assessment, and provide constructive feedback to benefit both potential customers and the company providing the product or service."`,
        name: 'Melly YMW',
        status: 'CEO of an eduport',
    },

    {
        image: '/src/assets/images/face.jpg',
        feedback: `"This product has transformed the way we work! The user experience is fantastic, and the customer support is top-notch. Highly recommended!"`,
        name: "Jack Itch",
        status: "customer"
    },

    {
        image: '/src/assets/images/face.jpg',
        feedback: `"This service is incredible! It made our workflow so much smoother and efficient. We're thrilled with the results!"`,
        name: "Emily Davis",
        status: "Marketing Director"
    }, 
]);

function updateHref() {
  const href = `#${index.value}`;
  document.getElementById('left-arrow').href = href;
  document.getElementById('right-arrow').href = href;
  console.log(href);
}

function prevSlide() {
    if (index.value > 0) {
        index.value--;
    }

    console.log(index)
    updateHref()
}

function nextSlide() {
    if (index.value < slides.value.length - 1) {
        index.value++;
    }

    updateHref()
}
</script>


<template>
    <div class="slider-container">
        <div class="slider">
            <div v-for="(slide, i) in slides" :key="i" class="slide" :id="i">
                <img :src="slide.image" alt="" />
                <div class="slide__info">
                    <div class="slide__info-feedback">
                        {{ slide.feedback }}
                    </div>
                    
                    <div class="slide__info-feedback-owner">
                        <div class="slide__info-name">{{ slide.name }}</div>
                        <div class="slide__info-status">{{ slide.status }}</div>
                    </div>
                </div>
            </div>
        </div>

        <div class="slider__nav">
            <a href="#" class="arrow" id="left-arrow" @click="prevSlide">
                <arrow-forward-icon />
            </a>

            <a href="#" class="arrow" id="right-arrow" @click="nextSlide">
                <arrow-forward-icon />
            </a>
        </div>
    </div>
</template>


<style scoped>
    .slider-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        position:relative;
        width: 80%;
        max-width: 80rem;
        margin:0 auto;
        background-color: #f0f0f0;
        box-shadow:0 1.5rem 3rem -0.75rem hsla(0,0%,0%,0.25);
        padding: 3rem 10px 3rem 10px;
        gap: 2rem;
        border-radius: 10px;
    }
    
    .slider {
        display:flex;
        overflow-x: hidden;
        scroll-snap-type:x mandatory;
        scroll-behavior:smooth;
        -webkit-scroll-behavior: smooth;
        -moz-scroll-behavior: smooth;
        width: 100%;
    }

    .slide {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 4rem;
        flex:1 0 100%;
        scroll-snap-align:start;
    }

    .slide__info-feedback {
        font-size: 1.6rem;
        font-family: var(--merriweather-font);
        font-style: italic;
        font-weight: 600;
        margin-bottom: 15px;
        text-align: center;
        padding: 0 15px 0 15px;
    }

    .slide__info-feedback-owner {
        font-family: var(--secondary-font);
    }
    
    .slide__info-feedback-owner {        
        margin-top: 3rem;
        text-align: center;
    }

    .slide__info-name {
        margin: 20px;
        font-size: 20px;
        font-weight: bold;
    }

    .slide img {
        width: 9rem;
        aspect-ratio: 1/1;
        object-fit: cover;
        border-radius: 50%;
        box-shadow: 0 15px 20px rgba(0, 0, 0, 0.5);
    }

    .slider__nav{
        display: flex;
        gap: 2rem;
        /* position: absolute;
        bottom: 1.5rem;
        left: 50%;
        transform: translateX(-50%); */
        z-index: 20;
    }

    .slider__nav a {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 3rem;
        height: 3rem;
        background-color: #000;
        border-radius: 50%;
        border: 2px solid transparent;
        text-decoration: none;
        transition: all .2s ease;
    }

    .slider__nav a:hover {
        background-color: #fff;
        border: 2px solid #000;
    }

    .slider__nav a:hover * {
        fill: #000;      
    }

    .slider__nav a > * {
        fill: #fff;
    }

    .slider__nav #left-arrow {
        transform: rotate(180deg);
    }

    @media (max-width: 768px) {
        .slide__info-feedback {
            font-size: 20px;
        }

        .slide__info-name,
        .slide__info-status {
            font-size: 15px;
        }
    }

    @media (max-width: 534px) {
        .slider-container {
            width: 90%;
        }

        .slide__info-feedback {
            margin: 0 auto;
            text-align: center;
        }
    }
</style>