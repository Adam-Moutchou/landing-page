<script setup>
import BaseServiceBox from '../BaseServiceBox.vue';
import PencilIcon from '../icons/PencilIcon.vue';
import InkPenIcon from '../icons/InkPenIcon.vue';
import BullHornIcon from '../icons/BullHornIcon.vue';
import PaletteIcon from '../icons/PaletteIcon.vue';
import ManSpeakIcon from '../icons/ManSpeakIcon.vue';
import DiamondIcon from '../icons/DiamondIcon.vue';

import { shallowRef } from 'vue';

const services = shallowRef([
    {title: "Content Marketing", body: "Our team creates engaging and shareable content that resonates with your audience, drives organic traffic", icon: PencilIcon},

    {title: "Graphic Design", body: "Unlock the power of visual storytelling with our expert graphic design services tailored to elevate your brand and captivate.", icon: InkPenIcon},

    {title: "Digital Marketing", body: "Elevate your brand's online presence with our data-driven digital marketing strategies. From SEO and content marketing", icon: BullHornIcon},

    {title: "Web Design", body: "We specialize in creating visually stunning, user-friendly websites that align with your brand identity and deliver an exceptional.", icon: PaletteIcon},

    {title: "IT Consulting", body: "IT consulting, or information technology consulting, refers to the practice of providing advisory and implementation services", icon: ManSpeakIcon},

    {title: "Brand Identity", body: "It involves creating a unique and recognizable identity that sets the brand apart from competitors and resonates with the target audience.", icon: DiamondIcon}
])
</script>


<template>
    <div class="services-section">
        <h3 class="services__headline">Our Services</h3>
        <h1 class="services__bigger-headline">High-impact services for your business</h1>
        <div class="services__grid">
            <base-service-box v-for="service in services" :key="service.title">
            <template v-slot:icons>
                <component :is="service.icon"></component> 
            </template>

            <template v-slot:info>
                <h2 class="service__title">{{ service.title }}</h2>
                <p class="service__description">{{ service.body }}</p>
            </template>
            </base-service-box>
        </div>
    </div>
</template>


<style scoped>
    .services-section {
        background-color: var(--secondary-color);
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 5rem;
        padding-bottom: var(--section-bottom-space);
    }

    .services__headline {
        text-align: center;
        color: var(--secondary-text-color);
        font-size: 2.5rem;
        font-family: var(--merriweather-font);
    }

    .services__bigger-headline {
        text-align: center;
        font-family: var(--merriweather-font);
        font-size: 3.5rem;
        width: 50rem;
    }

    @media (max-width: 736px) {
        .services__bigger-headline {
            width: 100%;
            font-size: 2rem;
            margin: 0 1rem 0 1rem;
        }

        .services__headline {
            font-size: 1.5rem;
        }
    }

    .service__title {
        font-family: var(--merriweather-font);
        margin: 0 0 15px 0;
    }

    .service__description {
        font-family: var(--secondary-font);
        font-size: 15px;
        text-align: justify;
    }

    .services__grid {
        --box-min-width: 27rem;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(var(--box-min-width), 1fr));
        gap: 2rem;
        width: 90%;
    }

    @media (max-width: 488px) {
        .services__grid {
            --box-min-width: 20rem;
        }
    }
</style>