<script setup>
import { FaBandsFacebookF, FaBandsXTwitter, FaBandsInstagram } from '@kalimahapps/vue-icons'
import { ref } from 'vue'

const active = ref('Home');
const links = ["Home", "Services", "About Us", "Contact Us"]
const emits = defineEmits(["clickInside"]);
const toggleMenu = (link) => {
    active.value = link;
    emits("clickInside");
}
</script>

<template>
    <nav class="text-white">
        <h2 class="font-bold text-xl">Precision Auto Body</h2>
        <ul class="gap-y-8 mt-4">
            <li class="mt-4" v-for="link of links" :key="link">
                <a @click="()=>toggleMenu(link)" :href="'#' + link.replace(' Us', '')" :class="`${active === link ? 'active' : ''}`">{{ link }}</a>
            </li>
        </ul>
        <ul class="flex mt-10 md:gap-4 gap-8">
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