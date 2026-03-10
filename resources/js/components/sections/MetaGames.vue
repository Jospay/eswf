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
        `Opisyal itong magiging available sa publiko sa February 2025. Maaari namang ma-enjoy ng mga player ang early access nito sa darating na Enero. #News5 | via Lui Urgino`,
    ],
};

const metaGames = {
    image: '/assets/partnersmeta.png',
    title: [
        'Multi-Cultural Sports',
        'ESFW Member Nations',
        'Esports',
        'Meta Movement',
        'Traditional Sports',
        'Professional and Amateur Sports',
        'Active / Digital/ Visual Sports',
    ],
    color: [
        '#1BAF6B',
        'white',
        '#137DC1',
        '#101215',
        '#FBD408',
        '#d9d9d9',
        '#E94140',
    ],
};

const worldcupcards = {
    cards: [
        '/assets/worldcup1.jpg',
        '/assets/worldcup2.jpg',
        '/assets/worldcup3.jpg',
        '/assets/worldcup4.jpg',
        '/assets/worldcup5.jpg',
    ],
};

const isExpanded = ref(false);

const toggleReadMore = () => {
    isExpanded.value = !isExpanded.value;
};
</script>

<template>
    <section class="w-full overflow-hidden sm:overflow-visible">
        <div
            class="relative z-10 mx-auto mt-6 mb-6 flex w-full max-w-6xl items-center justify-center px-4 sm:mt-8 sm:mb-8 sm:px-6 md:mb-12 lg:px-8"
        >
            <img
                src="https://img.youtube.com/vi/s60-MGhb-Tk/maxresdefault.jpg"
                alt="ESWF Anniversary Background"
                class="h-auto w-full rounded-xl object-cover shadow-lg sm:rounded-2xl"
            />
        </div>

        <div
            class="flex justify-center px-4 py-2 text-center text-2xl font-semibold text-[#137DC1] sm:py-4 sm:text-3xl md:text-4xl lg:text-5xl"
        >
            GridLock Games feature on TV Patrol
        </div>

        <div class="flex justify-center px-4 py-6 sm:py-8">
            <a
                href="https://www.youtube.com/watch?v=s60-MGhb-Tk"
                target="_blank"
                rel="noopener noreferrer"
                class="inline-flex w-full items-center justify-center gap-2 rounded-xl bg-[#E94140] px-6 py-3 text-sm font-bold text-white shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-[#CC0000] hover:shadow-lg sm:w-auto sm:px-10 sm:py-4 sm:text-base md:px-12 md:text-lg"
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

    <section
        class="mx-auto grid max-w-400 grid-cols-1 items-start gap-8 px-6 py-8 md:grid-cols-1 md:gap-12 md:px-16 md:py-12 lg:grid-cols-2"
    >
        <figure class="sticky top-8 w-full">
            <img
                :src="article.image"
                :alt="article.imageAlt"
                class="h-auto w-full rounded-3xl object-cover shadow-lg"
            />
        </figure>

        <article
            class="flex w-full flex-col items-start gap-4 overflow-hidden md:gap-6"
        >
            <h2
                class="max-w-3xl text-3xl leading-snug font-bold text-balance wrap-break-word text-[#137DC1] sm:text-2xl md:text-2xl lg:text-5xl"
            >
                {{ article.title }}
            </h2>

            <div class="flex flex-col gap-4">
                <p
                    v-for="(paragraph, index) in article.paragraphs"
                    :key="index"
                    v-show="index < 2 || isExpanded"
                    class="text-base leading-relaxed text-gray-900 transition-all duration-500 md:text-lg dark:text-gray-300"
                >
                    {{ paragraph }}
                </p>
            </div>

            <button
                @click="toggleReadMore"
                class="mt-2 inline-flex cursor-pointer items-center gap-2 rounded-xl bg-[#137DC1] px-8 py-3 text-base font-semibold text-white shadow-md transition-colors duration-300 hover:bg-[#4089f7] hover:shadow-lg md:text-lg"
            >
                {{ isExpanded ? 'See less' : 'See more' }}

                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 transition-transform duration-300"
                    :class="{ 'rotate-180': isExpanded }"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                >
                    <path
                        fill-rule="evenodd"
                        d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                        clip-rule="evenodd"
                    />
                </svg>
            </button>
        </article>
    </section>

    <section
        class="mx-auto grid max-w-400 grid-cols-1 items-center gap-2 px-2 py-6 md:gap-12 md:px-16 md:py-12 lg:grid-cols-3"
    >
        <div class="col-span-1 flex justify-center lg:justify-start">
            <img
                :src="metaGames.image"
                alt="Meta Games Partners"
                class="h-auto w-full max-w-sm rounded-xl object-cover sm:rounded-2xl"
            />
        </div>

        <div
            class="col-span-1 grid w-full grid-cols-1 gap-4 sm:grid-cols-2 sm:gap-6 lg:col-span-2"
        >
            <div
                v-for="(title, index) in metaGames.title"
                :key="index"
                class="flex items-center gap-4 rounded-full bg-white p-4 shadow-md shadow-blue-300 transition-all duration-300 hover:-translate-y-1 hover:shadow-lg dark:bg-neutral-700"
            >
                <div
                    class="h-10 w-10 shrink-0 rounded-full shadow-inner sm:h-12 sm:w-12"
                    :style="{ backgroundColor: metaGames.color[index] }"
                ></div>

                <span
                    class="text-base font-semibold text-gray-800 sm:text-lg dark:text-gray-200"
                >
                    {{ title }}
                </span>
            </div>
        </div>
    </section>

   <section class="w-full overflow-hidden sm:overflow-visible">
        <div class="flex justify-center px-4 py-2 text-center text-2xl font-semibold text-[#137DC1] sm:py-4 sm:text-3xl md:text-4xl lg:text-5xl">
            ESWF General Assembly
        </div>
        <div class="relative z-10 mx-auto mt-6 mb-6 flex w-full max-w-6xl items-center justify-center px-4 sm:mt-8 sm:mb-8 sm:px-6 md:mb-12 lg:px-8">
            <img
                src="/assets/digitalgems.png"
                alt="ESWF Anniversary Background"
                class="h-auto w-full rounded-xl object-cover shadow-lg sm:rounded-2xl"
            />
        </div>

        <div class="flex justify-center px-4 py-2 text-center text-2xl font-semibold text-[#137DC1] sm:py-4 sm:text-3xl md:text-4xl lg:text-5xl">
            ESWF World Cup
        </div>
        
        <div class="mx-auto w-full max-w-400 px-4 py-8 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 gap-12 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5">
                <div 
                    v-for="(card, index) in worldcupcards.cards" 
                    :key="index"
                    class="overflow-hidden rounded-4xl shadow-md shadow-blue-300 transition-all duration-300 hover:-translate-y-1 hover:shadow-xl"
                >
                    <img 
                        :src="card" 
                        alt="World Cup Card" 
                        class="h-full w-full object-cover"
                    />
                </div>
            </div>
        </div>
    </section>
</template>
