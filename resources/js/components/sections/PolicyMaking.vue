<script setup lang="ts">
import { ref, onMounted, watch, nextTick } from 'vue';

interface HeaderProps {
    headerImage?: string;
    title?: string;
}

const props = withDefaults(defineProps<HeaderProps>(), {
    headerImage: '/assets/policy.jpg',
    title: 'Policy making Bodies of Esports Genres Federations',
});

// 9 profiles with individual toggle states
const profiles = ref([
    {
        name: 'Mark Hatter',
        role: 'President MMORPG',
        profilePicture: '/assets/p1.png',
        backGroundPicture: '/assets/p1.jpg',
        flag: '/assets/p1f.jpg',
        description: 'Oversees the global MMORPG electronic sports division, focusing on large-scale competitive raids and PvP tournaments.',
        showDetails: false
    },
    {
        name: 'Arniel O. Gutierrez',
        role: 'President and Founder',
        profilePicture: '/assets/p2.png',
        backGroundPicture: '/assets/p2.jpg',
        flag: '/assets/p2f.jpg',
        description: 'The visionary founder of the federation, dedicated to standardizing esports policies worldwide.',
        showDetails: false
    },
    {
        name: 'Andy Koh',
        role: 'President',
        profilePicture: '/assets/p3.png',
        backGroundPicture: '/assets/p3.jpg',
        flag: '/assets/p3f.jpg',
        description: 'President Asia Pacific Electronic Sports Confederation, managing regional qualifiers and development programs.',
        showDetails: false
    },
    {
        name: 'Juan Dela Cruz',
        role: '',
        profilePicture: '/assets/p4.png',
        backGroundPicture: '/assets/p4.jpg',
        flag: '/assets/p4f.jpg',
        description: '',
        showDetails: false
    },
    {
        name: 'Timothy Shen',
        role: 'Global Ambassador',
        profilePicture: '/assets/p5.png',
        backGroundPicture: '/assets/p5.jpg',
        flag: '/assets/pf5.jpg',
        description: 'CEO & Founder Yesports Media Group',
        showDetails: false
    },
    {
        name: 'Vinay Java',
        role: 'Founder and CEO Barrix Esports',
        profilePicture: '/assets/p6.png',
        backGroundPicture: '/assets/p6.jpg',
        flag: '/assets/p6f.jpg',
        description: 'Coordinates international LAN events, ensuring venue standards and broadcast quality.',
        showDetails: false
    },
    {
        name: 'Ivan Brinklow',
        role: 'President International Federation of eSports Rhythm Games',
        profilePicture: '/assets/p7.png',
        backGroundPicture: '/assets/p7.jpg',
        flag: '/assets/p7f.jpg',
        description: 'and Chair of Regional MetaSports Commission.',
        showDetails: false
    },
    {
        name: 'Paolo Blasi',
        role: 'President: ESWF Italy',
        profilePicture: '/assets/p8.png',
        backGroundPicture: '/assets/p8.jpg',
        flag: '/assets/p8f.jpg',
        description: 'National President: MetaSports Governing Body',
        showDetails: false
    },
    {
        name: 'Leonard Loftus',
        role: 'Deputy President: ESWF Member Nations',
        profilePicture: '/assets/p9.png',
        backGroundPicture: '/assets/p9.jpg',
        flag: '/assets/p9f.jpg',
        description: 'President: ESWF South Africa National President: MetaSports Governing Body',
        showDetails: false
    },
    {
        name: 'Juan Dela Cruz',
        role: '',
        profilePicture: '/assets/p10.png',
        backGroundPicture: '/assets/p10.jpg',
        flag: '/assets/p10f.jpg',
        description: '',
        showDetails: false
    }
]);

const showAllProfiles = ref(false);

// Function to initialize Owl Carousel safely
const initCarousel = () => {
    const $ = (window as any).$;
    if ($ && !showAllProfiles.value) {
        $('.profile-carousel').owlCarousel({
            loop: false, 
            margin: 32, // Equivalent to Tailwind's gap-8
            nav: false, // REMOVED the left/right arrows
            dots: false, // REMOVED the dots at the bottom
            responsive: {
                0: { items: 1 },
                640: { items: 2 },
                768: { items: 3 } // Shows 3 at a time just like your grid
            }
        });
    }
};

// Initialize when page loads
onMounted(() => {
    initCarousel();
});

// Re-initialize carousel ONLY when switching back from Grid to Carousel
watch(showAllProfiles, async (isShowingAll) => {
    if (!isShowingAll) {
        await nextTick(); // Wait for Vue to render the DOM
        initCarousel();
    }
});
</script>

<template>
    <header class="relative flex w-full max-w-7xl mx-auto my-4 sm:my-8 items-center justify-center rounded-2xl sm:rounded-3xl overflow-hidden px-4 sm:px-8 md:px-16 min-h-17.5 sm:min-h-25 lg:min-h-37.5">
        <div class="absolute inset-0 z-0">
            <img :src="props.headerImage" alt="Hero Background" class="h-full w-full object-cover object-center" />
            <div class="absolute inset-0 dark:bg-black/30 bg-black/10"></div>
        </div>
        <div class="relative z-10 flex flex-col items-center justify-center w-full max-w-5xl text-white text-center">
            <h1 class="text-xl sm:text-xl md:text-2xl lg:text-3xl font-semibold drop-shadow-lg px-2 sm:px-4 py-8 md:py-12 leading-snug md:leading-tight">
                {{ props.title }}
            </h1>
        </div>
    </header>

    <section class="w-full max-w-7xl mx-auto px-4 py-6">
        
        <div v-if="!showAllProfiles" class="max-w-5xl mx-auto">
            <div class="owl-carousel owl-theme profile-carousel">
                <div 
                    v-for="(person, index) in profiles" 
                    :key="'carousel-' + index" 
                    class="relative flex flex-col w-full h-full bg-white p-3 dark:bg-gray-800 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-100 dark:border-gray-700 mx-auto"
                >
                    <div class="relative w-full aspect-square shadow-md shadow-blue-300 z-10 overflow-hidden shrink-0">
                        <img :src="person.backGroundPicture" alt="Background" class="w-full h-full object-cover" />
                        <img :src="person.flag" alt="Country Flag" class="absolute top-3 right-3 w-8! h-6! object-cover rounded-[2px]! shadow-sm border border-white" />
                    </div>
                    
                    <div class="relative flex justify-center -mt-12 z-20 shrink-0">
                        <img :src="person.profilePicture" alt="Profile" class="w-24! h-24! rounded-full! object-cover border-4 border-white dark:border-gray-800 bg-gray-100" />
                    </div>
                    
                    <div class="flex flex-col items-center justify-start text-center px-4 pt-2 pb-6 grow rounded-b-2xl overflow-hidden z-0">
                        <h2 class="text-xl sm:text-lg lg:text-xl font-bold text-[#137DC1] dark:text-[#3da0e6] w-full truncate">{{ person.name }}</h2>
                        <p class="text-gray-900 dark:text-gray-300 text-sm font-medium mt-1 w-full truncate">{{ person.role }}</p>
                        
                        <button @click="person.showDetails = !person.showDetails" class="inline-flex items-center gap-2 rounded-lg bg-[#137DC1] px-6 py-1.5 mt-4 text-sm font-medium text-white transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] cursor-pointer">
                            {{ person.showDetails ? 'Hide Details' : 'Show Details' }}
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 transition-transform duration-300" :class="person.showDetails ? 'rotate-180' : ''" viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                            </svg>
                        </button>
                        <p v-if="person.showDetails && person.description" class="text-gray-700 dark:text-gray-300 text-sm mt-4 animate-fade-in">{{ person.description }}</p>
                    </div>
                </div>
            </div>
        </div>

        <div v-else class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
            <div 
                v-for="(person, index) in profiles" 
                :key="'grid-' + index" 
                class="relative flex flex-col w-full h-full bg-white p-3 dark:bg-gray-800 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-100 dark:border-gray-700"
            >
                <div class="relative w-full aspect-square shadow-md shadow-blue-300 z-10 overflow-hidden shrink-0">
                    <img :src="person.backGroundPicture" alt="Background" class="w-full h-full object-cover" />
                    <img :src="person.flag" alt="Country Flag" class="absolute top-3 right-3 w-8 h-6 object-cover rounded-[2px] shadow-sm border border-white" />
                </div>
                
                <div class="relative flex justify-center -mt-12 z-20 shrink-0">
                    <img :src="person.profilePicture" alt="Profile" class="w-24 h-24 rounded-full object-cover border-4 border-white dark:border-gray-800 bg-gray-100" />
                </div>
                
                <div class="flex flex-col items-center justify-start text-center px-4 pt-2 pb-6 grow rounded-b-2xl overflow-hidden z-0">
                    <h2 class="text-xl sm:text-lg lg:text-xl font-bold text-[#137DC1] dark:text-[#3da0e6] w-full truncate">{{ person.name }}</h2>
                    <p class="text-gray-900 dark:text-gray-300 text-sm font-medium mt-1 w-full truncate">{{ person.role }}</p>
                    
                    <button @click="person.showDetails = !person.showDetails" class="inline-flex items-center gap-2 rounded-lg bg-[#137DC1] px-6 py-1.5 mt-4 text-sm font-medium text-white transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] cursor-pointer">
                        {{ person.showDetails ? 'Hide Details' : 'Show Details' }}
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 transition-transform duration-300" :class="person.showDetails ? 'rotate-180' : ''" viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                        </svg>
                    </button>
                    <p v-if="person.showDetails && person.description" class="text-gray-700 dark:text-gray-300 text-sm mt-4 animate-fade-in">{{ person.description }}</p>
                </div>
            </div>
        </div>

        <div class="mt-12 flex justify-center pb-2">
            <button
                @click="showAllProfiles = !showAllProfiles"
                class="inline-flex items-center gap-2 rounded-lg bg-[#137DC1] px-10 py-2 text-base font-medium text-white transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] md:text-lg cursor-pointer"
            >
                {{ showAllProfiles ? 'Show Less' : 'See All' }}
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 transition-transform duration-300"
                    :class="showAllProfiles ? 'rotate-180' : ''"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                >
                    <path
                        fill-rule="evenodd"
                        d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
                        clip-rule="evenodd"
                    />
                </svg>
            </button>
        </div>
    </section>
</template>

<style scoped>
/* Scrollbars & Animations */
.custom-scrollbar {
    scrollbar-width: thin;
    scrollbar-color: #137DC1 transparent; 
}
.custom-scrollbar::-webkit-scrollbar { width: 10px; }
.custom-scrollbar::-webkit-scrollbar-track { background: transparent; }
.custom-scrollbar::-webkit-scrollbar-thumb {
    background-color: #004dd1; 
    border-radius: 10px;
}
@media (prefers-color-scheme: dark) {
    .custom-scrollbar { scrollbar-color: #2465c0 transparent; }
    .custom-scrollbar::-webkit-scrollbar-thumb { background-color: #006aff; }
}

.animate-fade-in { animation: fadeIn 0.3s ease-in-out; }
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(-5px); }
    to { opacity: 1; transform: translateY(0); }
}
</style>