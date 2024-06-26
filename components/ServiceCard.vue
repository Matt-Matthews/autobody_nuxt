<script setup>
const props = defineProps({
    title: {
        type: String,
        required: true
    },
    desc: {
        type: String,
        required: true
    },
    imgUrl: {
        required: true
    }
})
</script>

<template>
    <div
        class="min-h-44 drop-shadow-sm shadow-black bg-white flex flex-col py-3 justify-center items-center rounded-md">
        <img :src="imgUrl" :alt="title">
        <h5 class="font-bold my-2">{{ title }}</h5>
        <p class="w-11/12 text-center card-desc font-medium lg:text-sm sm:text-xs">{{ desc }}</p>
    </div>
</template>
<style scoped>
div {
    width: calc(33.3% - 13.3px);
    box-shadow: black 0px;
}
@media (max-width: 1242px) {
    div {
        width: calc(50% - 10px);
    }
}
@media (max-width: 639px) {
    div {
        width: 100%;
    }
    p {
        font-size: 0.75rem;
        line-height: 1rem;
    }
}
</style>