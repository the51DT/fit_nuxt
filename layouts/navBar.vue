<template>
    <header class="w-full flex justify-between items-center guide-header__wrap">
        <!-- 사이트 제목 -->
        <h1 class="text-xl font-semibold">
            <NuxtLink :to="siteData?.path || '/'" id="siteTitle">{{ siteData?.siteName || 'Fit Team Library' }}</NuxtLink>
        </h1>
    
        <!-- 네비게이션 -->
        <nav class="navi relative">
            <button @click="toggleMenu" class="text-white focus:outline-none">☰</button>
            <ul v-if="isMenuOpen">
            <li v-for="item in iaData?.IaList" :key="item.id">
                <NuxtLink :to="`${item.path}${item.link || ''}`" class="block px-4 py-2">
                {{ item.Level1 }}
                </NuxtLink>
            </li>
            </ul>
        </nav>
    </header>
</template>

<script setup>
    import { ref, onMounted } from 'vue';
    
    const iaData = ref(null);
    const siteData = ref(null);
    const isMenuOpen = ref(true);
    
    // JSON 데이터 불러오기
    onMounted(async () => {
        try {
        const response = await fetch('/ia.json');
        if (!response.ok) throw new Error('JSON 파일을 불러올 수 없습니다.');
        const data = await response.json();
        
        iaData.value = data;
        siteData.value = data.siteName ? { siteName: data.siteName, path: '/' } : null;
        } catch (error) {
        console.error('JSON 불러오기 오류:', error);
        }
    });
    
    // 네비게이션 메뉴 토글
    const toggleMenu = () => {
        isMenuOpen.value = !isMenuOpen.value;
    };
</script>

<style scoped>
    .navi button {
        @apply text-xl bg-transparent border-none cursor-pointer;
    }
</style>