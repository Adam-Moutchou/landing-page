<script setup>
import BaseButton from '../BaseButton.vue';
import { ref, onMounted } from 'vue';

// Disclamer: This image slide is build with the help of chat-gpt
const currentIndex = ref(0);

const slides = ref([
  {
    src: '../src/assets/images/team.jpg',
    alt: 'group-of-people-putting-up-their-fist',
  },
  {
    src: '../src/assets/images/team2.jpg',
    alt: 'photo-of-people-smiling-and-posing-for-a-picture',
  },
  {
    src: '../src/assets/images/team3.jpg',
    alt: 'group-of-people-standing-infront-of-blackboard',
  }
]);

const getSlideClass = (index) => {
    if (index === currentIndex.value) return 'active';
    if (index === (currentIndex.value + 1) % slides.value.length) return 'inactive1';
    if (index === (currentIndex.value + 2) % slides.value.length) return 'inactive2';
    return '';
}

const showNextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % slides.value.length;
};

onMounted(() => {
  setInterval(showNextSlide, 7000);
});
</script>


<template>
    <div class="about-section">
        <div class="about-content">
            <div class="about__image">
                <!--Disclamer: This image slide is build with the help of chat-gpt -->
                <figure
                class="slide"
                v-for="(slide, index) in slides"
                :key="index"
                :class="getSlideClass(index)">
                
                <img :src="slide.src" :alt="slide.alt"/>

                </figure>
            </div>
            
            <div class="about__info">
                <div class="about__info-title">About Us</div>
                <div class="about__info-main">
                    <div class="about__info-main-headline">
                        <h2>The core mission behind all our work</h2>
                    </div>
    
                    <div class="about__info-main-mission">
                        <p>
                            We are dedicated to providing the best services to our clients. Our team is passionate about making
                            a difference and delivering high-quality solutions tailored to your needs.
                        </p>
                    </div>
    
                    <div class="about__info-numbers">
                        <div>
                            <span class="numbers">330+</span>
                            <p>Companies helped</p>
                        </div>
    
                        <div>
                            <span class="numbers">230+</span>
                            <p>Revenue generated</p>
                        </div>
                    </div>
                    
                    <div class="cta-button">
                        <base-button />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style scoped>
    .about-section {
        height: 100%;
        background-color: var(--primary-color);
        overflow: hidden;
        padding-bottom: var(--section-bottom-space);
    }

    .about-content {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 3rem;
        padding: 7rem;
        position: relative;
        margin: var(--section-bottom-space) 0 0 0;
    }

    /* Image slider */

    .about__image {
        --image-width: 100%;
        --image-height: 30rem;
        width: var(--image-width);
        height: var(--image-height);
        position: relative;
    }

    .slide {
        position: absolute;
        filter: grayscale(100%);
        transition: all .7s;
      }
      
    .slide.active {
        opacity: 1;
        filter: none;
        z-index: 100;
    }

    .slide img {
        border-radius: 10px;
        width: var(--image-width);
        height: var(--image-height);
        object-fit: cover;
    }
      
    .active {
        transform: translate(0);
    }
    
    .inactive1 {
      transform: translate(-30px, -30px);
      opacity: 0.3;
      z-index: 20;
    }

    .inactive2 {
        transform: translate(-60px, -60px);
        opacity: 0.2;
    }
    
    /* Image slider */
    .about__info {
        display: flex;
        flex-direction: column;
        gap: 3rem;
        color: #fff;
    }
    
    .about__info-title {
        color: var(--secondary-text-color);
        font-weight: bold;
        font-size: 20px;
    }
    
    .about__info-title,
    .about__info-main-mission,
    .about__info-numbers p {
        font-family: var(--secondary-font);
    }
    
    .about__info-title,
    .about__info-main-headline {
        font-family: var(--merriweather-font);
    }
    
    .about__info-numbers .numbers {
        color: var(--secondary-text-color);
        font-family: 'Times New Roman', Times, serif;
        font-size: 30px;
        font-weight: bold;
    }
    
    .about__info-main {
        display: flex;
        flex-direction: column;
        gap: 25px;
    }
    
    .about__info-main-headline {
        font-size: 1.7rem;
    }

    .about__info-numbers {
        display: flex;
        align-items: center;
        gap: 3rem;
    }
    
    @media (max-width: 814px) {
        .about-content {
            flex-direction: column;
        }

        .about__info-main-mission {
            text-align: justify;
        }

        .about__info-main-headline {
            width: 100%;
        }

        .inactive1, .inactive2 {
            transform: translate(0);
        }

        .about-content {
            padding: 2rem;
        }
    }

    @media (max-width: 510px) {
        .about-content {
            gap: 5rem;
            padding: 1rem;
        }

        .about__info {
            gap: 4rem;
        }

        .about__info-main {
            gap: 1.7rem;
        }

        .about__info-main-headline {
            font-size: 1.3rem;
        }

        .cta-button {
            align-self: center;
        }
    }
</style>
