<script setup>

</script>


<template>
    <div class="service">
        <div class="service__icon">
            <slot name="icons"></slot>            
        </div>

        <div class="service__info">
            <slot name="info"></slot>
        </div>
    </div>
</template>


<style scoped>
    .service {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        gap: 2.5rem;
        padding: 40px;
        background-color: var(--service-box-bg);
        /* width: 33rem; */
        border-radius: 10px;
        transition: background .2s;
    }

    
    .service__icon {
        width: 3.5rem;
        height: 3.5rem;
        background-color: var(--primary-color);
        display: grid;
        place-content: center;
        border-radius: 50%;
        overflow: hidden;
        fill: #fff;
    }
    
    .service__icon > * {
        width: 30px;
        height: 30px;
    }
    </style>