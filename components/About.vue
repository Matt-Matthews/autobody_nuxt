<script setup>
import points from '../utils/points.json'
</script>

<template>
    <div class="min-h-screen w-full p-8 text-black " id="About">
        <h2 class="font-bold text-3xl text-center">About Us</h2>
        <div class="w-full min-h-full flex flex-col lg:flex-row items-center justify-between mt-6">
            <img src="../assets/about.svg" alt="about" />
            <div class="lg:ml-20">
                <article>
                    <p class="font-medium">
                        We're more than just your average auto body shop. We're a team
                        of passionate enthusiasts dedicated to restoring your vehicle to
                        its peak condition, both aesthetically and functionally. We
                        understand the emotional connection you have with your car, and
                        our mission is to ensure it looks and drives as good as new, no matter
                        what life throws your way.
                    </p>
                    <h4>Our Commitment to Quality:</h4>
                    <p>We take pride in using only the highest quality materials and employing the latest repair
                        techniques. Our team of certified technicians undergoes continuous training to stay ahead of the
                        curve in the ever-evolving world of auto body repair.
                    </p>
                    <h4>What Makes Us Different:</h4>
                    <ol>
                        <li v-for="point of points" :key="point">
                            <p>{{ point }} </p>
                        </li>
                    </ol>
                </article>
            </div>
        </div>
    </div>
</template>
<style scoped>
img {
    width: 30%;
}

p {
    font-weight: 500;
}

h4 {
    margin-top: 1rem;
    margin-bottom: 0.25rem;
    font-weight: bold;
}

ol {
    list-style-type: disc;
    list-style-position: initial;
    margin-left: 25px;
}
@media (max-width: 1242px){
    img {
    width: 50%;
    margin-bottom: 1.5rem;
    }
} 
@media (max-width: 600px){
    img {
    width: 100%;
}
}
</style>