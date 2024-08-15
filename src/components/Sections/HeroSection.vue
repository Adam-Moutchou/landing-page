<script setup>
import Header from '../layouts/TheHeader.vue';        
import BaseButton from '../BaseButton.vue'
import Partners from '../layouts/ThePartners.vue'
</script>

<template>
    <div class="hero-section">
        <Header />

        <main>
            <div class="hero__info">
                <div class="hero__info-heading">
                    <img src="/src/assets/images/stars.png" class="stars" alt="">
                    <h1 class="main-text">Ready to take your <span>Business Growth</span> to the next level?</h1>
                </div>
                <!--Space-->
                <div class="sub-and-cta-container">
                    <p class="sub-text">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Atque laboriosam sequi minus suscipit? Cumque explicabo quae sit accusamus hic omnis dolorum, porro cum molestiae laborum facilis aperiam debitis accusantium rem!</p>
                    <base-button />                    
                </div>
                <!--Space-->
                <Partners class="partners-component"/>
            </div>

            <div class="hero__image">
                <div class="circle-border">
                    <img src="/src/assets/images/team-working.jpg" alt="">  
                </div>
            </div>
        </main>
    </div>
</template>

<style scoped>
    .hero-section {
        height: 120vh;
        background-color: var(--hero-background-color);
    }
    
    main {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 0 2rem 0 2rem;
    }

    .hero__info {
        display: flex;
        flex-direction: column;
        gap: 4rem;
    }    
    
    .main-text {
        color: #fff;
        font-family: var(--merriweather-font);
        font-size: 3.5rem;
        width: 45rem;
        position: relative;
    }

    .main-text span {
        color: var(--secondary-text-color);
    }

    .hero__info-heading {
        position: relative;
    }

    .stars {
        position: absolute;
        left: 0;
        transform: translateX(-40px);
        width: 13rem;
        opacity: 0.2;
    }

    .sub-text {
        color: #fff;
        font-family: var(--main-font);
        width: 40rem;
        text-align: justify;
    }

    .sub-and-cta-container {
        display: flex;
        flex-direction: column;
        gap: 20px;
        position: relative;
        z-index: 10;
    }

    .hero__image {
        --image-dimension: 24rem;
        position: relative;
    }
    
    .hero__image img {
        --image-shadow: rgba(129, 209, 236, 0.4);
        width: var(--image-dimension);
        height: var(--image-dimension);
        border-radius: 50%;
        object-fit: cover;
        box-shadow: 0px 0px 376px 0px var(--image-shadow);
        -webkit-box-shadow: 0px 0px 376px 0px var(--image-shadow);
        -moz-box-shadow: 0px 0px 376px 0px var(--image-shadow);
    }

    .hero__image::after {
        content: '';
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: calc(var(--image-dimension) + 4rem);
        height: calc(var(--image-dimension) + 4rem);
        border: 2px solid var(--secondary-text-color);
        border-radius: 50%;
        opacity: 0.3;
    }

    .hero__image .circle-border {
        width: calc(var(--image-dimension) + 8rem);
        height: calc(var(--image-dimension) + 8rem);
        border: 2px solid var(--secondary-text-color);
        border-radius: 50%;
        display: grid;
        place-content: center;        
        opacity: 0.7;
    }

    @media (max-width: 1258px) {
        .hero__image {
            display: none;
        }
    }

    @media (max-width: 742px) {
        .main-text {
            font-size: 2.3rem;
            width: 100%;
        }

        .hero__info {
            align-items: center;
        }

        .sub-text {
            width: 100%;
        }

        main {
            margin: 2rem 0 0 0;
            padding-left: 1rem;
            padding-right: 1rem;
        }
    }
</style>