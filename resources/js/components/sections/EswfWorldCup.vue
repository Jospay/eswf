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
    <section class="flex h-full w-full flex-col bg-white dark:bg-neutral-800">
        <header
            class="relative z-30 mt-5 flex items-center justify-center bg-[#137DC1] p-3 text-center text-xl font-medium text-white transition-colors sm:text-2xl md:text-4xl dark:bg-[#137DC1]/50"
        >
            ESWF World Cup 2026 Philippines
        </header>

        <div
            class="mt-8 flex w-full justify-center transition-all duration-500 ease-in-out sm:mt-12"
        >
            <div
                class="w-[50%] transition-all duration-500 ease-in-out sm:w-[45%] md:w-[40%] lg:w-[35%] xl:w-[30%]"
            >
                <div
                    class="w-full pt-[33.75%] transition-all duration-500 ease-in-out sm:pt-[28.125%]"
                ></div>
            </div>
        </div>

        <div
            class="relative mt-8 w-full transition-all duration-500 ease-in-out"
        >
            <div
                class="absolute inset-0 bg-transparent transition-colors duration-500 dark:bg-black/20"
            ></div>

            <img
                :src="bgImage"
                alt="Hero Background"
                class="block h-36 w-full object-cover object-center transition-all duration-500 ease-in-out sm:h-auto xl:h-full"
                loading="lazy"
            />

            <div
                class="group absolute top-0 left-1/2 z-20 w-[65%] -translate-x-1/2 -translate-y-[60%] transition-all duration-500 ease-in-out sm:w-[50%] sm:-translate-y-1/2 md:w-[45%] lg:w-[40%] xl:w-[35%]"
            >
                <div
                    class="flex aspect-video items-center justify-center overflow-hidden rounded-2xl bg-gray-100 shadow-2xl transition-all duration-500 ease-in-out"
                >
                    <div
                        class="absolute inset-0 bg-transparent transition-colors duration-500 dark:bg-black/10"
                    ></div>

                    <img
                        :src="contentImage"
                        class="h-full w-full object-cover transition-transform duration-500 ease-out group-hover:scale-105"
                        alt="Card Feature"
                        loading="lazy"
                    />
                </div>
            </div>
        </div>
    </section>
</template>
