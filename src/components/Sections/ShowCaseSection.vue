<script setup>
import NorthEastIcon from '../icons/NorthEastIcon.vue';
import BaseButton from '../BaseButton.vue'
import TheFeedBackSlider from '../layouts/TheFeedBackSlider.vue';
import TheFooter from '../layouts/TheFooter.vue';
</script>


<template>
    <div class="showcase-section">
        <h2 class="showcase__headline">Recent Showcase</h2>

        <div class="showcase__grid">
            <div class="showcase__grid-item">
                <a href="#example" target="__blank">
                    <img src="/src/assets/images/paper-flower.jpg" alt="">
                    <div class="up-arrow">
                        <north-east-icon />
                    </div>
                </a>
                <h3 class="showcase__grid-item-headline">Web UI design</h3>
                <p>Create UI design</p>
            </div>

            <div class="showcase__grid-item">
                <a href="#example" target="__blank">
                    <img src="/src/assets/images/sunset.jpg" alt="">
                    <div class="up-arrow">
                        <north-east-icon />
                    </div>
                </a>

                <h3 class="showcase__grid-item-headline">UI  Design</h3>
                <p>Creative Rebranding for logo</p>

            </div>

            <div class="showcase__grid-item">
                <a href="#example" target="__blank">
                    <img src="/src/assets/images/nature.png" alt="">
                    <div class="up-arrow">
                        <north-east-icon />
                    </div>
                </a>

                <h3 class="showcase__grid-item-headline">To design Digital Strategy</h3>
                <p>Social Media Marketing</p>
                
            </div>

            <div class="showcase__grid-item">
                <a href="#example" target="__blank">
                    <img src="/src/assets/images/earth.jpg" alt="">
                    <div class="up-arrow">
                        <north-east-icon />
                    </div>
                </a>
    
                <h3 class="showcase__grid-item-headline">UI  Design</h3>
                <p>Creative Rebranding for logo</p>
            </div>
        </div>

        <div class="cta-button">
            <base-button apparence="light"/>
        </div>

        <div class="feedback-slider">
            <the-feed-back-slider />
        </div>

        <the-footer />
    </div>
</template>


<style scoped>
    .showcase-section {
        background-color: var(--secondary-color);
    }

    .showcase__headline {
        text-align: center;
        font-size: 3rem;
        font-family: var(--merriweather-font);
        margin-bottom: 1rem;
    }

    .showcase__grid {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
        gap: 5rem;
        width: 90%;
        margin: 0 auto;
    }

    .showcase__grid-item img {
        width: 30rem;
        height: 20rem;
        object-fit: cover;
        border-radius: 15px;
    }

    .showcase__grid-item a {
        position: relative;
        display: block;
    }

    .showcase__grid-item .up-arrow {
        position: absolute;
        top: 2rem;
        right: 2rem;
        width: 2.5rem;
        height: 2.5rem;
        background-color: rgb(0, 0, 0,0.7);
        display: grid;
        place-content: center;
        border-radius: 50%;
        padding: 20px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
        backdrop-filter: blur(10px);
    }

    .showcase__grid-item {
        display: flex;
        flex-direction: column;
        gap: 10px;
        width: 30rem;
    }

    .showcase__grid-item-headline {
        font-family: var(--merriweather-font);
        font-size: 22px;
    }

    .showcase__grid-item p {
        font-family: var(--secondary-font);
    }

    @media (max-width: 490px) {
        .showcase__grid-item img {
            width: 100%;
        }

        .showcase__headline {
            font-size: 2rem;
        }
    }

    .cta-button {
        margin: 0 auto;
    }

    .feedback-slider {
        margin-top: 2rem;
    }
</style>