<script setup lang="ts">
import { ref, onMounted, watch, nextTick } from 'vue';

const worldItems = [
  { id: 1, title: "Esports For all" },
  { id: 2, title: "Women’s Esports" },
  { id: 3, title: "Challenged (Person With Disabilities) Esports" },
];

const continentalRegional = ref([
    {
        title: 'Asia Pacific Electronic Sports Confederation – Apescon',
        backGroundPicture: '/assets/conti1.jpg',
        description: 'Asia Pacific Electronic Sports Confederation (Apescon) The leading continental Esports For All organization it includes East Asia, South Asia ,South East Asia and Oceania',
        websiteUrl: 'https://www.facebook.com/apescon?_rdc=1&_rdr#', 
        showDetails: false
    },
    {
        title: 'Amateur Europe Esports Federation (AEEF)',
        backGroundPicture: '/assets/conti2.jpg',
        description: 'The Governing body of Esports for All in Europe',
        websiteUrl: 'https://www.facebook.com/people/Europe-Esports-Federation-for-Amateurs/100064117839716/', 
        showDetails: false
    },
    {
        title: 'Americas Esports Federation Organization – Amesfo',
        backGroundPicture: '/assets/conti3.jpg',
        description: 'The Governing body of Esports For All in America.',
        websiteUrl: 'https://www.facebook.com/people/Americas-Esports-Federation-Organization-Amesfo/100064930470200/', 
        showDetails: false
    },
    {
        title: 'Organization of African Electronic Sports – OAES',
        backGroundPicture: '/assets/conti4.jpg',
        description: 'The Governing Body of Esports for all in Africa',
        websiteUrl: 'https://www.facebook.com/people/Organization-of-African-Electronic-Sports-OAES/100069674842208/', 
        showDetails: false
    },
    {
        title: 'MENA ESPORTS CUP',
        backGroundPicture: '/assets/conti5.jpg',
        description: 'Middle East & North Africa Esport Federation',
        websiteUrl: 'https://example.com', 
        showDetails: false
    },
    {
        title: 'South East Asia Esports Cup',
        backGroundPicture: '/assets/conti5.jpg',
        description: 'South East Asia Esports Confederation',
        websiteUrl: '', 
        showDetails: false
    },
    {
        title: 'Americas Esports Cup',
        backGroundPicture: '/assets/conti6.jpg',
        description: 'Americas Esports Cup.',
        websiteUrl: 'https://www.facebook.com/people/Americas-Esports-Cup/100065028937721/', 
        showDetails: false
    },
    {
        title: 'Asia Pacific Esports Cup',
        backGroundPicture: '/assets/conti7.jpg',
        description: 'Asia Pacific Esports Cup.',
        websiteUrl: 'https://www.facebook.com/people/Asia-Pacific-Esports-Cup/100064688499136/', 
        showDetails: false
    },
    {
        title: 'African Esports Cup',
        backGroundPicture: '/assets/conti8.jpg',
        description: 'African Esports Cup',
        websiteUrl: 'https://www.facebook.com/people/African-Esports-Cup/100064324943855/', 
        showDetails: false
    },
    {
        title: 'European Esports Cup',
        backGroundPicture: '/assets/conti9.jpg',
        description: 'President: ESWF South Africa National President: MetaSports Governing Body',
        websiteUrl: 'https://www.facebook.com/people/European-Esports-Cup/100065062716007/', 
        showDetails: false
    },
    
]);

const showAllProfiles = ref(false);

const initCarousel = () => {
    const $ = (window as any).$;
    if ($ && !showAllProfiles.value) {
        $('.profile-carousel').owlCarousel({
            loop: false, 
            margin: 32, 
            nav: false, 
            dots: false,
            responsive: {
                0: { items: 1 },
                640: { items: 2 },
                768: { items: 3 }
            }
        });
    }
};

onMounted(() => {
    initCarousel();
});

watch(showAllProfiles, async (isShowingAll) => {
    if (!isShowingAll) {
        await nextTick(); 
        initCarousel();
    }
});

</script>

<template>
  <section class="w-full bg-white py-8 dark:bg-neutral-800">
    <header
      class="relative z-30 mt-5 flex items-center justify-center bg-[#137DC1] p-6 text-center text-xl font-medium text-white transition-colors sm:text-2xl md:text-4xl dark:bg-[#137DC1]/50 fade-in-up"
    >
      Continental And Regional Esports Cup
    </header>
  
    <div class="flex justify-center p-6 text-center text-4xl font-semibold text-[#137DC1] fade-in-up">
      ESWF World Cup Categories
    </div>
    
    <div class="mx-auto grid max-w-7xl grid-cols-1 gap-6 px-4 py-3 md:grid-cols-3">
      <div 
        v-for="(item, index) in worldItems" 
        :key="item.id" 
        class="flex flex-row items-center gap-4 rounded-xl bg-gray-50 p-4 shadow-sm dark:bg-gray-800 fade-in-up"
        :style="{ animationDelay: `${index * 100}ms` }"
      >
        <div class="flex h-16 w-16 shrink-0 items-center justify-center rounded-xl bg-[#137DC1] text-3xl font-bold text-white">
          {{ item.id }}
        </div>
        
        <div class="flex flex-col overflow-hidden">
          <h2 class="text-xl font-medium text-gray-900 md:text-2xl dark:text-white">
            {{ item.title }}
          </h2>
        </div>
      </div>
    </div>
    
    <section class="w-full mx-auto px-4 py-6 items-center bg-[#137DC1]">
        <h2 class="flex justify-center text-center text-white text-4xl font-semibold py-3 fade-in-up">Continental And Regional Esports Cup</h2>
        
        <div v-if="!showAllProfiles" class="max-w-5xl mx-auto fade-in-up">
            <div class="owl-carousel owl-theme profile-carousel">
                <div 
                    v-for="(person, index) in continentalRegional" 
                    :key="'carousel-' + index" 
                    class="relative flex flex-col w-full h-full bg-white p-3 dark:bg-gray-800 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-100 dark:border-gray-700 mx-auto"
                >
                    <div class="relative w-full aspect-square z-10 overflow-hidden shrink-0">
                        <img :src="person.backGroundPicture" alt="Background" class="w-full h-full object-cover" />
                    </div>
                    
                    <div class="flex flex-col items-center justify-start text-center px-4 pt-4 pb-6 grow rounded-b-2xl z-0">
                        <h2 class="text-xl sm:text-lg lg:text-xl font-bold text-black dark:text-white w-full">{{ person.title }}</h2>
                        
                        <div class="flex flex-col items-center gap-2 mt-4 w-full">
                            <button @click="person.showDetails = !person.showDetails" class="inline-flex items-center justify-center gap-2 rounded-lg bg-[#137DC1] px-6 py-2 text-sm font-medium text-white transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] cursor-pointer w-full">
                                {{ person.showDetails ? 'Hide Details' : 'Show Details' }}
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 transition-transform duration-300" :class="person.showDetails ? 'rotate-180' : ''" viewBox="0 0 20 20" fill="currentColor">
                                    <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                                </svg>
                            </button>
                            
                            <a :href="person.websiteUrl" target="_blank" rel="noopener noreferrer" class="inline-flex items-center justify-center gap-2 rounded-lg bg-yellow-400 px-6 py-2 text-sm font-medium text-gray-800 transition-all duration-300 hover:-translate-y-1 hover:bg-yellow-500 cursor-pointer w-full">
                                View Website
                            </a>
                        </div>
                        
                        <p v-if="person.showDetails && person.description" class="text-gray-700 dark:text-gray-300 text-sm mt-4 animate-fade-in">{{ person.description }}</p>
                    </div>
                </div>
            </div>
        </div>

        <div v-else class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
            <div 
                v-for="(person, index) in continentalRegional" 
                :key="'grid-' + index" 
                class="relative flex flex-col w-full h-full bg-white p-3 dark:bg-gray-800 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-100 dark:border-gray-700 fade-in-up"
                :style="{ animationDelay: `${(index % 3) * 100}ms` }"
            >
                <div class="relative w-full aspect-square z-10 overflow-hidden shrink-0">
                    <img :src="person.backGroundPicture" alt="Background" class="w-full h-full object-cover" />
                </div>
                
                <div class="flex flex-col items-center justify-start text-center px-4 pt-4 pb-6 grow rounded-b-2xl z-0">
                    <h2 class="text-xl sm:text-lg lg:text-xl font-bold text-black dark:text-white w-full">{{ person.title }}</h2>
                    
                    <div class="flex flex-col items-center gap-2 mt-4 w-full">
                        <button @click="person.showDetails = !person.showDetails" class="inline-flex items-center justify-center gap-2 rounded-lg bg-[#137DC1] px-6 py-2 text-sm font-medium text-white transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] cursor-pointer w-full">
                            {{ person.showDetails ? 'Hide Details' : 'Show Details' }}
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 transition-transform duration-300" :class="person.showDetails ? 'rotate-180' : ''" viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                            </svg>
                        </button>
                        
                        <a :href="person.websiteUrl" target="_blank" rel="noopener noreferrer" class="inline-flex items-center justify-center gap-2 rounded-lg bg-yellow-400 px-6 py-2 text-sm font-medium text-gray-800 transition-all duration-300 hover:-translate-y-1 hover:bg-yellow-500 cursor-pointer w-full">
                            View Website
                        </a>
                    </div>
                    
                    <p v-if="person.showDetails && person.description" class="text-gray-700 dark:text-gray-300 text-sm mt-4 animate-fade-in">{{ person.description }}</p>
                </div>
            </div>
        </div>

        <div class="mt-12 flex justify-center pb-2 fade-in-up">
            <button
                @click="showAllProfiles = !showAllProfiles"
                class="inline-flex items-center gap-2 rounded-lg bg-white px-10 py-2 text-base font-bold text-[#137DC1] transition-all duration-300 hover:-translate-y-1 hover:bg-gray-100 md:text-lg cursor-pointer shadow-md"
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
  </section>
</template>

<style scoped>
.fade-in-up {
    opacity: 0;
    animation: fadeInUp 0.6s ease-out forwards;
}

@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.animate-fade-in {
    animation: fadeIn 0.4s ease-in-out forwards;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}
</style>