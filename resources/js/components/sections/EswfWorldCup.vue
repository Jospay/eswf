<script setup lang="ts">
import { computed } from 'vue';

interface SectionData {
    image_path?: string | null;
}

interface Props {
    sectionData?: SectionData | null;
}

const props = withDefaults(defineProps<Props>(), {
    sectionData: null,
});

const CONFIG = {
    FALLBACK_BG_IMAGE: '/assets/bgchamp.jpg',
    FALLBACK_CONTENT_IMAGE: '/assets/eswfchamp.jpg',
    STORAGE_PREFIX: '/storage/',
};

// 5. Clean, predictable computed properties
const bgImage = computed(() => {
    return props.sectionData?.image_path
        ? `${CONFIG.STORAGE_PREFIX}${props.sectionData.image_path}`
        : CONFIG.FALLBACK_BG_IMAGE;
});

const contentImage = computed(() => {
    return props.sectionData?.image_path
        ? `${CONFIG.STORAGE_PREFIX}${props.sectionData.image_path}`
        : CONFIG.FALLBACK_CONTENT_IMAGE;
});
</script>
<template>
    <section class="w-full h-full bg-white flex flex-col">
        <header class="relative z-30 flex items-center justify-center p-3 mt-5 text-xl font-medium text-white transition-colors bg-[#137DC1] sm:text-2xl md:text-4xl text-center">
            ESWF World Cup 2026 Philippines
        </header>

        <div class="w-full flex justify-center mt-8 sm:mt-12 transition-all duration-500 ease-in-out">
            <div class="w-[50%] sm:w-[45%] md:w-[40%] lg:w-[35%] xl:w-[30%] transition-all duration-500 ease-in-out">
                <div class="w-full transition-all duration-500 ease-in-out pt-[33.75%] sm:pt-[28.125%]"></div>
            </div>
        </div>

        <div class="relative w-full mt-8 transition-all duration-500 ease-in-out">
            <img
                :src="bgImage"
                alt="Hero Background"
                class="block w-full h-36 sm:h-auto xl:h-full object-cover object-center transition-all duration-500 ease-in-out"
                loading="lazy"
            />

            <div class="absolute top-0 left-1/2 z-20 w-[65%] sm:w-[50%] md:w-[45%] lg:w-[40%] xl:w-[35%] -translate-x-1/2 -translate-y-[60%] sm:-translate-y-1/2 transition-all duration-500 ease-in-out group">
                
                <div class="overflow-hidden shadow-2xl rounded-2xl aspect-video bg-gray-100 flex items-center justify-center transition-all duration-500 ease-in-out">
                    <img
                        :src="contentImage"
                        class="object-cover w-full h-full transition-transform duration-500 ease-out group-hover:scale-105"
                        alt="Card Feature"
                        loading="lazy"
                    />
                </div>

            </div>
        </div>
    </section>
</template>