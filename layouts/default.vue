<template>
    <div class="layout-container">
        <main>
            <navBar v-if="!isHomePage" />
            <slot />
        </main>
    </div>
</template>

<script setup>
import { useRoute } from 'vue-router';
import NavBar from '@/layouts/navBar.vue';
const route = useRoute();
const isHomePage = route.path === '/' || route.path === '';
</script>