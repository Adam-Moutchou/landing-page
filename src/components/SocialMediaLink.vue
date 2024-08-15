<script setup>
defineProps(['mediaLink']);
</script>


<template>
    <div class="media-link">
        <a :href="mediaLink" target="__blank">
            <slot></slot>        
        </a>
    </div>
</template>


<style scoped>
    .media-link {
        --main-bg: #fff;
        --fill-color: #000;
        width: 2.5rem;
        height: 2.5rem;
        background-color: var(--main-bg);
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        border: 2px solid transparent;
        transition: all .2s ease;
    }

    .media-link a {
        display: grid;
        place-content: center;
    }

    .media-link a > * {
        width: 30px;
        height: 30px;
    }

    .media-link:hover {
        background-color: var(--secondary-text-color);
        border: 2px solid var(--main-bg);
    }
</style>