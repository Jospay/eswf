<script setup lang="ts">
// Grouping all the content into a single data object makes it easy to edit later
const gabArticle = {
    image: 'assets/games.jpg',
    imageAlt: 'GAB Courtesy Visit',
    title: 'Games and Amusements Board',
    paragraphs: [
        '[24 February 2025] - Esports World Federation (ESWF) President Arniel Gutierrez, along with ESWF members Chong C.S., Jun Lasco, and Kevin Balhetchet, made a courtesy visit to GAB Chairman Atty. Francisco J. Rivera.',
        '“The Philippines is home to a number of the world’s legendary esports players. We look forward to striking a meaningful partnership with the ESWF to maintain the high level of prestige and standing of our local esports players and elevate esports to new heights,” said GAB Chairman Atty. Rivera.'
    ],
    linkUrl: 'https://www.facebook.com/100064530678864/posts/1029283105899369/?rdid=dcw7hOTuo40g8ExK#',
    linkText: 'Visit Website'
};
</script>

<template>
    <section class="flex flex-col w-full bg-white dark:bg-neutral-800">
        <div class="w-full pt-24 sm:pt-32 transition-all duration-500 ease-in-out"></div>

        <div class="relative flex w-full flex-col items-center bg-[#137DC1] transition-colors duration-500">
            
            <div class="absolute top-0 left-1/2 z-20 w-[65%] -translate-x-1/2 -translate-y-1/2 transition-all duration-500 ease-in-out sm:w-[50%] md:w-[45%] lg:w-[40%] xl:w-[35%]">
                <div class="group flex aspect-video items-center justify-center overflow-hidden rounded-2xl bg-gray-100 shadow-2xl transition-all duration-500 ease-in-out">
                    <div class="absolute inset-0 z-10 bg-transparent transition-colors duration-500 dark:bg-black/10 pointer-events-none"></div>
                    
                    <img
                        :src="gabArticle.image"
                        :alt="gabArticle.imageAlt"
                        class="h-full w-full object-cover transition-transform duration-500 ease-out group-hover:scale-105"
                        loading="lazy"
                    />
                </div>
            </div>

            <div class="w-[65%] transition-all duration-500 ease-in-out sm:w-[50%] md:w-[45%] lg:w-[40%] xl:w-[35%]">
                <div class="w-full pt-[28.125%]"></div>
            </div>

            <div class="w-full max-w-6xl px-6 pb-20 pt-10 text-center sm:px-12">
                <div class="space-y-6 text-base font-medium text-white sm:text-lg md:text-xl">
                    
                    <h1 class="mb-4 text-2xl font-bold drop-shadow-sm sm:text-3xl md:text-4xl">
                        {{ gabArticle.title }}
                    </h1>
                    
                    <p 
                        v-for="(paragraph, index) in gabArticle.paragraphs" 
                        :key="index"
                        class="leading-relaxed text-white/95"
                    >
                        {{ paragraph }}
                    </p>

                </div>
            </div>

            <div class="flex justify-center pb-6">
                <a
                    :href="gabArticle.linkUrl"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center gap-2 rounded-xl bg-white dark:bg-black px-8 py-3.5 text-sm font-semibold text-[#137DC1] shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] hover:shadow-lg sm:px-12 sm:text-base md:px-16 md:text-lg hover:text-white"
                >
                    {{ gabArticle.linkText }}
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 sm:h-6 sm:w-6" viewBox="0 0 20 20" fill="currentColor">
                        <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                    </svg>
                </a>
            </div>
            
        </div>
    </section>
</template>