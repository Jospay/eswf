<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps({
    sectionData: {
        type: Object,
        default: () => null
    }
});

const bgImage = computed(() => {
    return props.sectionData?.image_path 
        ? `/storage/${props.sectionData.image_path}` 
        : '/assets/bghome.jpg';
});

const defaultTitle = 'Esports World Federation World Cup';
const defaultContent = `An international esports competition platform organized to bring together players, teams, and federations from around the world. It aims to promote electronic sports across multiple game genres, support talent development, and provide a global stage for inclusive competitive gaming.`;
</script>

<template>
    <div id="home" class="relative w-full min-h-[34rem] h-auto overflow-hidden bg-neutral-900">
        
        <div class="absolute inset-0 w-full h-full">
            <img 
                :src="bgImage" 
                alt="Hero Background" 
                class="w-full h-full object-cover object-center"
            >
            <div class="absolute inset-0"></div>
        </div>

        <div class="relative h-full flex flex-col items-center justify-center pt-18 pb-12 px-6 text-center">
            
            <div class="hero-content max-w-7xl mx-auto w-full space-y-6">
                
                <h1 class="text-white text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-black tracking-tight drop-shadow-2xl leading-tight">
                    {{ sectionData?.title || defaultTitle }}
                </h1>

                <p class="text-white/90 text-sm sm:text-base md:text-lg lg:text-xl max-w-6xl mx-auto drop-shadow-md font-medium leading-relaxed whitespace-pre-wrap">
                    {{ sectionData?.content || defaultContent }}
                </p>
                
            </div>
        </div>
    </div>
</template>

<style scoped>
.hero-content {
    animation: fadeIn 1s ease-out forwards;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}
</style>