<script setup>
import SocialMediaLink from '../SocialMediaLink.vue';
import FaceBookIcon from '../icons/FaceBookIcon.vue';
import InstagramIcon from '../icons/InstagramIcon.vue';
import LinkedDin from '../icons/LinkedDin.vue';
import { shallowRef } from 'vue';

const socialMedias = shallowRef([
    { icon: FaceBookIcon, title: "Facebook", link: "https:facebook.com" },
    { icon: InstagramIcon, title: "Instagram", link: "https:instagram.com" },
    { icon: LinkedDin, title: "Linkedin", link: "https:linkedin.com"}
]);
</script>


<template>
    <footer>
        <div class="footer-section">
            <div class="footer-section__logo">
                <img src="/src/assets/images/logo.png" alt="">
                <p>We're a team of strategic creator and digital innovator, united focus in our pursuit of mastery and joyful.</p>
            </div>

            <div class="footer-section__links">
                <div class="links">
                    <h3>Pages</h3>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">Home 2</a></li>
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Contact Us</a></li>
                        <li><a href="#">Portfolio</a></li>
                        <li><a href="#">Portfolio Single</a></li>
                    </ul>
                </div>
                
                <div class="links">
                    <h3>Utility Pages</h3>
                    <ul>
                        <li><a href="#">Style Guide</a></li>
                        <li><a href="#">Instructions</a></li>
                        <li><a href="#">Licence</a></li>
                        <li><a href="#">ChangeLog</a></li>
                        <li><a href="#">Error 404</a></li>
                        <li><a href="#">Password Protected</a></li>
                    </ul>
                </div>
            </div>
            

            <div class="footer-section__subscription">
                <label for="subscription">
                    <h3>Subscribe</h3>
                    <div>
                        <input type="email" name="email" id="subscription" placeholder="Enter your email here">
                        <button type="submit">Subscribe</button>
                    </div>
                </label>
            </div>
        </div>

        
        <div class="footer-section__info">
            <hr />
            <div class="footer-info">
                <div class="info">
                    <h3>Copyright By</h3>
                    <p>Designed by Iconstica.com</p>
                </div>
    
                <div class="info">
                    <h3>Contact us:</h3>
                    <p class="phone-number">+123 456 7890</p>
                </div>
    
                <div class="info">
                    <h3>Adress:</h3>
                    <p>123 Main Street, City, Country</p>
                </div>
    
                <div class="social-media__links">
                    <social-media-link v-for="media in socialMedias" :key="media.title" :media-link="media.link" :title="media.title">
                        <component :is="media.icon"></component>
                    </social-media-link>
                </div>
            </div>
        </div>
    </footer>
</template>


<style scoped>
    footer {
        --text-color: #fff;
        background-color: var(--primary-color);
        padding: 0 20px 0 20px;
    }

    footer h3 {
        color: var(--text-color);
        font-family: var(--merriweather-font);
        font-size: var(--footer-heading-fontSize); 
    }

    .footer-section {
        display: flex;
        align-items: center;
        justify-content: space-around;
        height: 25rem;
        position: relative;
    }

    .footer-section__logo img {
        width: 10rem;
        aspect-ratio: 2/1;
        object-fit: cover;
        margin-bottom: 15px;
    }
    
    .footer-section__logo p {
        color: var(--text-color);
        font-family: var(--secondary-font);
        width: 30rem;
    }

    .footer-section__links {
        display: flex;
        justify-content: space-between;
        gap: 10rem;
        height: 70%;
        align-items: flex-end;
    }

    .footer-section .links {
        display: flex;
        flex-direction: column;
        gap: 15px;
    }

    .footer-section__links a {
        text-decoration: none;
        color: var(--text-color);
        transition: color .1s ease;
    }

    .footer-section__links a:hover {
        color: var(--secondary-text-color);
    }

    /* .footer-section__links h3 {
        color: var(--text-color);
        font-family: var(--merriweather-font);
        font-size: var(--footer-heading-fontSize);
    } */

    .footer-section__links li {
        list-style-type: none;
        padding: 4px;
        font-family: var(--secondary-font);
    }

    
    .footer-section__subscription label {
        display: block;
        color: var(--text-color);
        font-size: 23px;
        font-family: var(--merriweather-font);
    }

    .footer-section__subscription label input {
        padding: 0 10px 0 10px;
        font-size: 17px;
        font-family: var(--secondary-font);
        border-radius: 200px;
        border: none;
        background-color: rgba(0, 0, 0, 0);
        outline: none;
        width: 100%;
    }

    .footer-section__subscription label div {
        background-color: #fff;
        border-radius: 200px;
        padding: 7px;
        margin: 10px 0 0 0;
        display: flex;
        align-items: center;
        width: 100%;
    }

    .footer-section__subscription label button {
        padding: 12px 15px 12px 15px;
        font-size: 15px;
        font-family: var(--secondary-font);
        border-radius: 200px;
        border: none;
        background-color: #000;
        color: var(--text-color);
        cursor: pointer;
        transition: all .1s;
    }

    .footer-section__subscription label button:hover {
        color: var(--secondary-text-color);
    }

    .footer-section__subscription label button:active {
        transition: none;
        opacity: 0.8;
    }

    
    .footer-info {
        display: flex;
        align-items: center;
        justify-content: space-around;
        color: #fff;
        padding: 2rem 0 2rem 0;
    }

    .social-media__links {
        display: flex;
        align-items: center;
        gap: 1rem;
    }

    .footer-info .info h3 {
        font-size: calc(var(--footer-heading-fontSize) - 4px) !important;
    }

    .footer-info .info p {
        font-family: var(--main-font);
        margin-top: 8px;
    }

    .footer-info .info .phone-number {
        color: var(--secondary-text-color);
    }

    .footer-section__info hr {
        width: 95%;
        margin: 0 auto;
    }

    @media (max-width: 1172px) {
        .footer-section {
            flex-direction: column;
            align-items: flex-start;
            height: 100%;
            gap: 3rem;
            margin: 0 0 3rem 0;
        }
    }

    @media (max-width: 840px) {
        .footer-info {
            flex-direction: column;
            align-items: flex-start;
            gap: 2.5rem;
        }

        .social-media__links {
            gap: 2rem;
            /* align-self: center; */
        }
    }

    @media (max-width: 484px) {
        .footer-section__logo p {
            width: 100%;
        }

        .footer-section__links {
            flex-direction: column;
            gap: 3rem;
        }

        .footer-section__links .links {
            width: 100%;
        }
    }
</style>