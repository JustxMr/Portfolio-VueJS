<script setup>
import { computed } from 'vue';
import { useRoute } from 'vue-router';
import HeaderHome from './components/HeaderHome.vue';
import FooterPage from './components/FooterPage.vue';

// Utilisation de useRoute pour accéder à la route actuelle
const route = useRoute();

// Computed pour déterminer si la route actuelle est NotFound
const isNotFound = computed(() => route.name === 'NotFound');
</script>

<template>
    <div class="headerhome">
        <HeaderHome v-if="!isNotFound" />
    </div>

    <RouterView/> 

    <div class="footerpage">
        <FooterPage v-if="!isNotFound" />
    </div>
</template>

<style scoped></style>
