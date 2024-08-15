<script setup>
import ArrowForwardIcon from './icons/ArrowForwardIcon.vue'        

defineProps(['apparence']);
</script>


<template>
    <a href="#Free-Trial" :class="apparence">
        <div class="free-trial">
            <div>
                <arrow-forward-icon />
            </div>
            <p>Start your Free Trial</p>  
        </div>
    </a> 
</template>


<style scoped>
    a {
        --main-color: #000;
        --second-color: #fff;
        --transition-duration: .2s;
        display: block;
        text-decoration: none;
        color: var(--main-color);
        font-size: 17px;
        font-weight: bold;
        font-family: var(--main-font);
        width: fit-content;
        transition: color var(--transition-duration) ease;
    }

    a.light {
        --main-color: #fff;
        --second-color: #000;
    }

    .free-trial {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 0.7rem;
        padding: var(--button-padding) 15px var(--button-padding) 15px;
        background-color: var(--second-color);
        width: fit-content;
        border-radius: var(--rounded-radius);
        border: 2px solid transparent;
        transition: all var(--transition-duration) ease;
    }
    

    .free-trial div {
        width: 2rem;
        height: 2rem;
        background-color: var(--main-color);
        display: grid;
        place-content: center;
        border-radius: 50%;
        fill: var(--second-color);
        transition: all var(--transition-duration) ease;
    }

    a:hover .free-trial {
        background-color: var(--main-color);
        border: 2px solid var(--second-color);
    }

    a:hover {
        color: var(--second-color);
    }

    a:hover div {
        background-color: var(--second-color);
        fill: var(--main-color);
    }

    a:active {
        color: var(--main-color);
    }

    a:active div {
        background-color: var(--main-color);
        fill: var(--second-color);
    }

    a:active .free-trial {
        background-color: var(--second-color);
        border: 2px solid transparent;

    }
</style>