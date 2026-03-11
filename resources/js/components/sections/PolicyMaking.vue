<script setup lang="ts">
interface HeaderProps {
    headerImage?: string;
    title?: string;
}

const props = withDefaults(defineProps<HeaderProps>(), {
    headerImage: '/assets/policy.jpg',
    title: 'Policy making Bodies of Esports Genres Federations',
});
</script>

<template>
    <header class="relative flex w-full max-w-7xl h-auto my-8 mx-auto items-center justify-center rounded-3xl overflow-hidden px-6 md:px-16">
        
        <div class="absolute inset-0 z-0">
            <img
                :src="props.headerImage"
                alt="Hero Background"
                class="h-full w-full object-cover object-center" 
            />
            <div class="absolute inset-0 dark:bg-black/30 bg-black/10"></div>
        </div>

        <div class="relative z-10 flex flex-col items-center justify-center w-full max-w-5xl text-white text-center">
            <h1 class="text-xl sm:text-4xl md:text-2xl lg:text-3xl font-semibold mb-2 drop-shadow-lg py-12">
                {{ props.title }}
            </h1>
        </div>
    </header>
</template>

<style scoped>
.custom-scrollbar {
    scrollbar-width: thin;
    scrollbar-color: #137DC1 transparent; 
}

.custom-scrollbar::-webkit-scrollbar {
    width: 10px;
}
.custom-scrollbar::-webkit-scrollbar-track {
    background: transparent;
}
.custom-scrollbar::-webkit-scrollbar-thumb {
    background-color: #004dd1; 
    border-radius: 10px;
}

/* Optional: Dark mode adjustments */
@media (prefers-color-scheme: dark) {
    .custom-scrollbar {
        scrollbar-color: #2465c0 transparent; 
    }
    .custom-scrollbar::-webkit-scrollbar-thumb {
        background-color: #006aff; 
    }
}
</style>