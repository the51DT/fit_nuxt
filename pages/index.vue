<template>
    <div>
        <div class="flex flex-col items-center justify-center w-full" :style="{ gap: '20px', height: '100vh' }">
            <div class="flex items-center justify-center  w-9/12"  style="gap: 20px">
                <NuxtLink to="#" class="btn-link">Vanilla</NuxtLink>
                <NuxtLink to="/guide/" class="btn-link">Vue</NuxtLink>
                <NuxtLink to="#" class="btn-link">React</NuxtLink>
            </div>
        </div>
    </div>
</template>

<style scoped>
.btn-link {
    @apply flex items-center justify-center w-full border rounded-md max-w-60 h-32 text-center bg-gray-200 text-xl font-semibold;
}
</style>