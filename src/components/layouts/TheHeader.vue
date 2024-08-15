<script setup>
import MenuIcon from '../icons/MenuIcon.vue';
import { ref } from 'vue'

const isSideBarActive = ref(true);

function toggleSideBar() {
    isSideBarActive.value = !isSideBarActive.value;
    const sideBar = document.querySelector(".side-bar");
    sideBar.focus();
}

function onBlur(e) {
    const sideBar = document.querySelector(".side-bar");

    if (sideBar.contains(e.relatedTarget)) {
        e.stopImmediatePropagation();
        console.log("Blur is stopped!")
        return;
    }
    
    isSideBarActive.value = true;
}
</script>

<template>
    <header>
        <div class="logo">
            <img src="/src/assets/images/logo.png" alt="">
        </div>

        <div class="side-bar" :class="{'side-bar--hidden': isSideBarActive, 'side-bar--shown': !isSideBarActive}" tabindex="0" @blur="onBlur">
            <nav>
                <a href="#Home">Home</a>
                <a href="#About-Us">About Us</a>
                <a href="#Contact-Us">Contact Us</a>
                <a href="#P">P</a>
                <a href="#PD">PD</a>
            </nav>

            <div class="get-touch">
                <a href="#Get-In-Touch">
                    Get in Touch
                </a>
            </div>

        </div>

        <div class="get-touch not-resp">
            <a href="#Get-In-Touch">
                Get in Touch
            </a>
        </div>

        <div class="humburger-menu" @click="toggleSideBar">
            <menu-icon />
        </div>
    </header>
</template>

<style scoped>
    header {
        display: flex;
        align-items: center;
        justify-content: space-around;
        position: relative;
    }

    header .logo img {
        width: 10rem;
        aspect-ratio: 2/1;
        object-fit: cover;
    }

    .side-bar {
        outline: none;
    }

    .side-bar nav a {
        padding: var(--button-padding);
        margin: 15px;
        text-decoration: none;
        color: var(--secondary-color);
        font-family: var(--main-font);
        font-size: 15px;
        position: relative;
        transition: color .1s;
    }

    .side-bar nav a::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        border-radius: var(--rounded-radius);
        width: 100%;
        height: 100%;
        transform: scaleY(0);
        mix-blend-mode: difference;
        background-color: var(--secondary-color); 
        transition: transform .2s ease-out;
    }

    .side-bar nav a:hover::before {
        transform: scaleY(1);
    }

    header .get-touch a {
        text-decoration: none;
        font-family: var(--main-font);
        padding: var(--button-padding) 20px var(--button-padding) 20px;
        border-radius: var(--rounded-radius);
        font-weight: bold;
        cursor: pointer;
        border: 2px solid transparent;
        transition: all .2s ease;
    }

    header .not-resp a {
        background-color: var(--secondary-color);
        color: var(--primary-color);
    }

    .side-bar .get-touch a {
       background-color: var(--primary-color);
       color: var(--secondary-color);
    }

    header .get-touch:hover a {
        background-color: rgba(0, 0, 0, 0);
        border: 2px solid var(--secondary-color);
        color: var(--secondary-color);
    }

    .side-bar .get-touch:hover a {
        background-color: rgba(0, 0, 0, 0);
        border: 2px solid var(--primary-color);
        color: var(--primary-color);
    }

    @media (min-width: 773px) {
        .humburger-menu {
            display: none;
        }

        .side-bar .get-touch {
            display: none;
        }
    }

    @media (max-width: 773px) {
        .side-bar {
            position: fixed;
            left: 0;
            bottom: 0;
            top: 0;
            background-color: #fff;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2rem;
            width: 13rem;
            z-index: 600;
        }

        .side-bar nav a {
            display: block;
            color: #000;
            width: fit-content;
            font-size: 20px;
        }

        .not-resp {
            display: none;
        }

        .side-bar--hidden {
            transform: translateX(-300px);
            transition: all .5s;
        }
    
        .side-bar--shown {
            transform: translateX(0);
            transition: all .5s;
        }
    }

    .humburger-menu {
        cursor: pointer;
    }


</style>