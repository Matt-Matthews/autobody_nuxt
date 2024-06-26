<script setup>
import { ServiceCard } from '.';
import {services} from '../utils/services.js'

</script>

<template>
    <div class="min-h-screen w-full p-8 light-blue relative text-black " id="Services">
        <h2 class="font-bold text-3xl text-center">Our Services</h2>
        <p class="lg:w-1/2 sm:w-10/12 mt-6 font-medium">At Precision Auto Body, we offer a comprehensive range of auto body repair
            and restoration services to bring your vehicle back to its pre-accident glory, or even better! We use
            the latest technologies and top-quality materials to ensure a flawless finish and long-lasting results.
            Here's what we can do for you:
        </p>
        <div class="w-full flex flex-wrap gap-5 mt-10">
            <ServiceCard v-for="{ title, desc, imgUrl } of services" :key="title" :imgUrl="imgUrl" :title="title"
                :desc="desc" />
        </div>
    </div>
</template>
<style scoped>
.icon {
    color: #3572EF;
    font-size: 33px;
}
</style>