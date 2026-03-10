<script setup lang="ts">
import { ref } from 'vue';

const article = {
    image: '/assets/thegame.jpg',
    imageAlt: 'Website promotion image',
    title: `Pinoy MOBA 'VI The Game' to Enter the World of ESPORTS`,
    paragraphs: [
        `Ipinakilala sa press ang pinakabagong aabangang Filipino-developed Mobo game na "Vi The Game" ngayon Miyerkules, Nov. 6.`,
        `Kasabay'yan ng isinagawang serenonya ng paglagda sa kasunduan ng partnership sa pagitan ng Department of Science and Technology #DOST at Esports World Federation #ESWF na layong suportahan ang “Vi the Game” sa planong pagpasok nito sa international Esports Arena.`,
        `Ang “Vi the Game” ay likha ng Filipino game development company na GridLock-Games Studio. Plano nila itong ipantapat sa sikat na MOBA games na nilalaro sa bansa kung saan namamayagpag ang galing ng Pinoy Esports players.`,
        `“Brace yourself for the next big thing in Esports! ‘Vi the Game’ delivers high-octane action, where strategy meets chaos. Dive into its unique ‘Corrupted Abyss’ mode and experience the thrill of surviving relentless monster waves while safeguarding your Ancient structure,” ayon sa developer nito.`,
        `Opisyal itong magiging available sa publiko sa February 2025. Maaari namang ma-enjoy ng mga player ang early access nito sa darating na Enero. #News5 | via Lui Urgino`
    ]
};

const isExpanded = ref(false);

const toggleReadMore = () => {
    isExpanded.value = !isExpanded.value;
};
</script>

<template>
  <section class="w-full overflow-hidden sm:overflow-visible">
    <div class="relative z-10 flex w-full max-w-6xl items-center justify-center mx-auto mt-6 mb-6 px-4 sm:mt-8 sm:mb-8 md:mb-12 sm:px-6 lg:px-8">
        <img 
          src="https://img.youtube.com/vi/s60-MGhb-Tk/maxresdefault.jpg" 
          alt="ESWF Anniversary Background" 
          class="h-auto w-full rounded-xl sm:rounded-2xl object-cover shadow-lg"
        >
    </div>

    <div class="flex justify-center px-4 py-2 text-center text-2xl font-semibold text-[#137DC1] sm:py-4 sm:text-3xl md:text-4xl lg:text-5xl">
      GridLock Games feature on TV Patrol
    </div>

    <div class="flex justify-center px-4 py-6 sm:py-8">
        <a
            href="https://www.youtube.com/watch?v=s60-MGhb-Tk"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex w-full items-center justify-center gap-2 rounded-xl bg-[#FF0000] px-6 py-3 text-sm font-bold text-white shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-[#CC0000] hover:shadow-lg sm:w-auto sm:px-10 sm:py-4 sm:text-base md:px-12 md:text-lg"
        >
            <span>Watch on YouTube</span>
            <svg 
                xmlns="http://www.w3.org/2000/svg" 
                class="h-5 w-5 sm:h-6 sm:w-6 md:h-7 md:w-7" 
                viewBox="0 0 24 24" 
                fill="currentColor"
            >
                <path d="M8 5v14l11-7z" />
            </svg>
        </a>
    </div>
  </section>

  <section class="grid grid-cols-1 md:grid-cols-1 lg:grid-cols-2 gap-8 md:gap-12 max-w-400 mx-auto px-6 md:px-16 py-8 md:py-12 items-start">
        <figure class="w-full sticky top-8">
            <img 
                :src="article.image" 
                :alt="article.imageAlt"
                class="w-full h-auto rounded-3xl object-cover shadow-lg"
            >
        </figure>

        <article class="flex flex-col items-start gap-4 md:gap-6 w-full overflow-hidden">
            <h2 class="text-[#137DC1] text-3xl sm:text-2xl md:text-2xl lg:text-5xl font-bold leading-snug max-w-3xl wrap-break-word text-balance">
                {{ article.title }}
            </h2>
            
            <div class="flex flex-col gap-4">
                <p 
                    v-for="(paragraph, index) in article.paragraphs" 
                    :key="index"
                    v-show="index < 2 || isExpanded"
                    class="text-gray-900 dark:text-gray-300 text-base md:text-lg leading-relaxed transition-all duration-500"
                >
                    {{ paragraph }}
                </p>
            </div>

            <button 
                @click="toggleReadMore"
                class="inline-flex items-center gap-2 bg-[#137DC1] text-white text-base md:text-lg font-semibold px-8 py-3 rounded-xl hover:bg-[#4089f7] transition-colors duration-300 shadow-md hover:shadow-lg mt-2 cursor-pointer"
            >
                {{ isExpanded ? 'See less' : 'See more' }}
                
                <svg 
                    xmlns="http://www.w3.org/2000/svg" 
                    class="h-5 w-5 transition-transform duration-300" 
                    :class="{ 'rotate-180': isExpanded }"
                    viewBox="0 0 20 20" 
                    fill="currentColor"
                >
                    <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                </svg>
            </button>
        </article>
    </section>
</template>