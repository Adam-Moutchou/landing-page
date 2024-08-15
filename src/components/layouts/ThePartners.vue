<script setup>
        
</script>

<template>
    <div class="partners-container">
        <p>Trusted by Leading Brands</p>
        <div class="partners">
            <img src="/src/assets/images/partner1.png" alt="">
            <img src="/src/assets/images/partner2.png" alt="">
            <img src="/src/assets/images/partner3.png" alt="">
            <img src="/src/assets/images/partner4.png" alt="">
        </div>
    </div>
</template>


<style scoped>
    .partners-container {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 1rem;
    }

    .partners-container p {
        color: var(--secondary-text-color);
        font-family: var(--main-font);
        font-weight: bold;
    }

    .partners img {
        width: 10rem;
        aspect-ratio: 2/1;
        object-fit: cover;
    }

    .partners {
        display: flex;
        align-items: center;
        gap: 2rem;
    }
    
    @media (max-width: 742px) {
        .partners img {
            width: 30%;
        }
        
        .partners {
            gap: 1rem;
            flex-wrap: wrap;
        }
    }
</style>