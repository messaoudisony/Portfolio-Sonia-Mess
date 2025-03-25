<script setup>
const props = defineProps({
        img: String,
        link: String,
        alt: String
})
</script>
<template>
    <a :href="props.link" target="_blanck">
    <img class="social-img" :src="`/src/assets/${props.img}.png`" :alt="props.alt" width="32px" color="white"/>
    </a>
</template>

<style scoped>
    .social-img {
        margin-right: 40px;
        filter: opacity(0.8);
        width: 50px;
        border: 3px solid var(--vt-v-custom-text-2);
        border-radius: 50%;
    }
    </style>