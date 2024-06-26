<script setup>
import { ref, onMounted } from 'vue'
import { FaBandsFacebookF, FaBandsXTwitter, FaBandsInstagram } from '@kalimahapps/vue-icons'

const links = ["Home", "Services", "About Us", "Contact Us"]
const year = ref('');
onMounted(() => {
    const date = new Date()
    year.value = date.getFullYear();
})
</script>

<template>
    <footer class="w-full bg-black h-1/3 text-white px-8 pt-4">
        <div class="md:flex text-center w-full items-center justify-between">
            <h2 class="font-bold text-xl">Precision Auto Body</h2>
            <ul class="flex flex-col gap-4 mt-8 md:mt-0">
                <li v-for="link of links" :key="link">
                    <a  :href="'#' + link.replace(' Us', '')">{{ link
                        }}</a>
                </li>
            </ul>
            <ul class="text-xs flex flex-col gap-4 mt-8 md:mt-0">
                <li>
                    <a href="tel:0123271668">+27 12 327 1668</a>
                </li>
                <li>
                    <a href="mailto: Info@PrecisionAutoBody.co.za">Info@PrecisionAutoBody.co.za</a>

                </li>
                <li>
                    <a
                        href="https://www.google.com/maps/place/406+Charlotte+Maxeke+St,+Pretoria+West,+Pretoria,+0183/@-25.7550926,28.1547561,17z/data=!3m1!4b1!4m6!3m5!1s0x1e956289b4151c6f:0xc62ef592cc2e42bd!8m2!3d-25.7550975!4d28.157331!16s%2Fg%2F11s8yq6l90?entry=ttu">406
                        Charlotte Maxeke St, Pretoria West, Pretoria, 0183</a>
                </li>
            </ul>
            <ul class="flex md:gap-4 gap-8 mt-8 md:mt-0">
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
        </div>
        <section class="w-full flex items-center justify-center mt-8">
            <small class="text-xs">© Copyrights reserved {{ year }}</small>
        </section>
    </footer>
</template>