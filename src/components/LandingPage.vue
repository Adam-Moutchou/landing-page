<script setup>
import HeroSection from './Sections/HeroSection.vue';        
import ServicesSection from './Sections/ServicesSection.vue';
import AboutSection from './Sections/AboutSection.vue';
import ShowCaseSection from './Sections/ShowCaseSection.vue';
</script>

<template>
    <div>
        <hero-section />
        <services-section />
        <about-section />
        <show-case-section />
    </div>
</template>

<style scoped>
    div {
        display: flex;
        flex-direction: column;
        gap: 5rem;
    }
</style>