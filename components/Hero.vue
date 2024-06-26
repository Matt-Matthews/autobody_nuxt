<script setup>
import { TopNav, MenuBtn, Menu } from '.';
import { ref } from 'vue'
import heroImg from '../assets/hero.svg'


const services = ["Maintenance", "Collision Repair", "spray & Paint", "Customization", "Scratch & Dent Removal", "Windshield Repair"]
const isMenuOpen = ref(false)
const toggleMenu = () => isMenuOpen.value = !isMenuOpen.value
const handleGetQuote = () => window.location.href = "#Contact"
</script>

<template>
    <div id="Home" class="h-screen w-full bg-img p-8 text-white relative" :style="{backgroundImage: 'URL('+heroImg+')'}">
        <TopNav />
        <MenuBtn :isMenuOpen="isMenuOpen" @toggleMenu="toggleMenu" />
        <div v-show="isMenuOpen" class="absolute h-full sm:w-2/3 md:w-1/3 bg-slate-800 top-0 left-0 menu p-8">
            <MenuBtn isMenuOpen @toggleMenu="toggleMenu" />
            <Menu @clickInside="toggleMenu" />
        </div>
        <div class="w-full h-full text-center flex flex-col justify-center items-center height">
            <h1 class="font-bold text-5xl">Quality Auto Body Repair Services</h1>
            <h3 class="font-bold text-3xl my-8">We bring your car back to life</h3>
            <button @click="handleGetQuote" class="mt-10">Get a Quote</button>
        </div>
    </div>
</template>

<style scoped>
.height {
    height: calc(100% - 48px);
}

.menu {
    display: none;
}

@media (max-width: 1023px) {
    .menu {
        display: block;
    }
}
.bg-img{
    background-image: heroImg;
}
</style>