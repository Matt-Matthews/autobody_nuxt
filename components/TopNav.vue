<script setup>
import {FaBandsFacebookF, FaBandsXTwitter, FaBandsInstagram} from '@kalimahapps/vue-icons'
import {ref} from 'vue'

const active = ref('Home');
const links = ["Home", "Services", "About Us", "Contact Us"]
</script>

<template>
    <nav class="text-white lg:flex h-12 justify-between items-center md:hidden z-20">
        <h2 class="font-bold text-xl">Precision Auto Body</h2>
        <ul class="flex gap-4">
            <li v-for="link of links" :key="link">
                <a @click="()=>{
                    active = link
                }" :href="'#'+link.replace(' Us', '')" :class="`${active === link? 'active':''}`" >{{ link }}</a>
            </li>
        </ul>
        <ul class="flex gap-4">
            <li><a href="#Facebook">
                <FaBandsFacebookF />
            </a></li>
            <li><a href="#Twitter">
                <FaBandsXTwitter />
            </a></li>
            <li><a href="#Instagram">
                <FaBandsInstagram />
            </a></li>
        </ul>
    </nav>
</template>
<style scoped>
    @media (max-width: 768px) {
    nav {
        display: none;
    }
}
</style>