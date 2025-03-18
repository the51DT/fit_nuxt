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
import NavBar from '/layouts/NavBar.vue'; // 네비게이션 컴포넌트 불러오기
const route = useRoute();
const isHomePage = route.path === '/' || route.path === ''; 
</script>