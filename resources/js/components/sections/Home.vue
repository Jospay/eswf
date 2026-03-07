<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted, nextTick } from 'vue';

// Tell TypeScript that jQuery ($) is globally available
declare var $: any;

const props = defineProps({
    sectionData: {
        type: Object,
        default: () => null,
    },
});

const bgImage = computed(() => {
    return props.sectionData?.image_path
        ? `/storage/${props.sectionData.image_path}`
        : '/assets/bghome.jpg';
});

const defaultTitle = 'Esports World Federation World Cup';
const defaultContent = `An international esports competition platform organized to bring together players, teams, and federations from around the world. It aims to promote electronic sports across multiple game genres, support talent development, and provide a global stage for inclusive competitive gaming.`;

// --- UTILITY: GET THUMBNAIL FROM LINK ---
const getCardImage = (item: any) => {
    if (item.image && item.image !== '') return item.image;
    const youtubeRegex = /(?:youtube\.com\/(?:[^\/]+\/.+\/|(?:v|e(?:mbed)?)\/|.*[?&]v=)|youtu\.be\/)([^"&?\/\s]{11})/;
    const match = item.link.match(youtubeRegex);
    if (match && match[1]) {
        return `https://img.youtube.com/vi/${match[1]}/maxresdefault.jpg`;
    }
    return '/assets/placeholder.jpg';
};

// --- CAROUSEL DATA ---
const carouselItems = ref([
    { title: 'ESWF Presentation ', image: '', link: 'https://www.youtube.com/watch?v=p81brupg4TM' },
    { title: 'ESWF World', image: '', link: 'https://www.youtube.com/watch?v=1CwxDW0XUHU&embeds_referring_euri=https%3A%2F%2Feswf.games%2F&source_ve_path=MjM4NTE' },
    { title: 'Collegiate Esports', image: '/assets/worldcup3.jpg', link: '#' },
    { title: 'World Cup Finals', image: '/assets/worldcup4.jpg', link: '#' },
]);

// --- OWL CAROUSEL LOGIC ---
const carouselRef = ref<HTMLElement | null>(null);

const initOwlCarousel = async () => {
    await nextTick();
    if (carouselRef.value && carouselItems.value.length > 0) {
        $(carouselRef.value).owlCarousel({
            loop: true,
            margin: 20,
            nav: false,
            dots: false,
            autoplay: true,
            autoplayTimeout: 5000,
            responsive: {
                0: { items: 1 },
                640: { items: 2 },
                1024: { items: 3 },
            },
        });
    }
};

const nextSlide = () => $(carouselRef.value).trigger('next.owl.carousel');
const prevSlide = () => $(carouselRef.value).trigger('prev.owl.carousel');

const shareCard = (title: string) => {
    if (navigator.share) {
        navigator.share({ title: title, url: window.location.href });
    } else {
        alert('Sharing link: ' + window.location.href);
    }
};

onMounted(() => initOwlCarousel());
onUnmounted(() => $(carouselRef.value).trigger('destroy.owl.carousel'));
</script>

<template>
    <div class="relative w-full bg-white dark:bg-neutral-800">
        <div
            id="home"
            class="relative w-full px-6 pt-24 pb-52 text-center"
        >
            <div class="absolute inset-0 z-0 h-full w-full overflow-hidden">
                <img
                    :src="bgImage"
                    alt="Hero Background"
                    class="h-full w-full object-cover opacity-100" 
                />
                <div class="absolute inset-0 dark:bg-black/30"></div> 
            </div>

            <div class="hero-content relative z-10 mx-auto w-full max-w-7xl space-y-6">
                <h1 class="text-4xl font-black tracking-tighter text-white drop-shadow-[0_2px_10px_rgba(0,0,0,0.8)] md:text-7xl">
                    {{ sectionData?.title || defaultTitle }}
                </h1>
                <p class="mx-auto max-w-6xl text-sm font-medium text-white drop-shadow-md md:text-lg">
                    {{ sectionData?.content || defaultContent }}
                </p>
            </div>
        </div>

        <div class="relative z-20 mx-auto -mt-32 w-full max-w-360 px-12 sm:px-20 md:px-24">
            
            <button
                @click="prevSlide"
                class="absolute top-1/2 left-0 z-30 -translate-y-1/2 transition-transform hover:scale-110 active:scale-95 md:left-4"
            >
                <img
                    src="/assets/larrow.png"
                    class="h-10 w-10 drop-shadow-lg md:h-16 md:w-16"
                    alt="Prev"
                />
            </button>
            
            <button
                @click="nextSlide"
                class="absolute top-1/2 right-0 z-30 -translate-y-1/2 transition-transform hover:scale-110 active:scale-95 md:right-4"
            >
                <img
                    src="/assets/rarrow.png"
                    class="h-10 w-10 drop-shadow-lg md:h-16 md:w-16"
                    alt="Next"
                />
            </button>

            <div ref="carouselRef" class="owl-carousel owl-theme">
                <div
                    v-for="(item, index) in carouselItems"
                    :key="index"
                    class="item group"
                >
                    <div
                        class="group relative aspect-video overflow-hidden rounded-3xl border-5 border-white bg-neutral-800 shadow-2xl transition-all duration-500 hover:-translate-y-2"
                    >
                        <div class="absolute inset-0 bg-linear-to-t from-[#137DC1] via-transparent to-transparent pointer-events-none"></div>
                        <img
                            :src="getCardImage(item)"
                            class="h-full w-full object-cover transition-transform duration-700 group-hover:scale-110"
                            alt="Card Image"
                        />
                        
                        <div class="absolute inset-0 flex items-center justify-center pointer-events-none">
                            <img 
                                src="/assets/video.png" 
                                class="w-12 h-12 object-contain drop-shadow-2xl transition-transform duration-300 group-hover:scale-125" 
                                alt="Play" 
                            />
                        </div>

                        <div class="absolute inset-0 flex flex-col justify-end bg-linear-to-t from-black/80 via-transparent to-transparent p-4">
                            <div class="flex items-center justify-between gap-3">
                                <a :href="item.link" class="flex-1">
                                    <h3 class="line-clamp-1 text-base font-bold text-white transition-colors group-hover:text-blue-400 sm:text-lg">
                                        {{ item.title }}
                                    </h3>
                                </a>

                                <button
                                    @click="shareCard(item.title)"
                                    class="rounded-full bg-white/20 p-2 text-white backdrop-blur-md transition-all hover:bg-white/40"
                                >
                                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-external-link-icon lucide-external-link"><path d="M15 3h6v6"/><path d="M10 14 21 3"/><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/></svg>
                                </button>
                            </div>
                        </div>

                        <a :href="item.link" class="absolute inset-0 z-0"></a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
/* Force same height */
:deep(.owl-stage) {
    display: flex;
    align-items: stretch;
}
:deep(.owl-item) {
    display: flex;
    flex: 1 1 auto;
}
:deep(.owl-item > .item) {
    width: 100%;
    display: flex;
}

.hero-content {
    animation: slideUp 0.8s ease-out forwards;
}

@keyframes slideUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}
</style>