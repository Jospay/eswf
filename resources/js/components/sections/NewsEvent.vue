<script setup lang="ts">
// 1. Existing Header Props
interface HeaderProps {
    headerImage?: string;
    title?: string;
    subtitle?: string; 
}

const props = withDefaults(defineProps<HeaderProps>(), {
    headerImage: '/assets/newsandeventbg.jpg',
    title: 'Esports World Federation',
    subtitle: 'News & Events',
});

// 2. Article Data
const article = {
    image: '/assets/news1.jpg',
    imageAlt: 'Website promotion image',
    title: 'DOST, CINCO Digital, ESWF, and BB88 Expand ENTER BATTLE ZONE 2026 to Include SALPAKAN and Vi the Game Competitions',
    content: 'Officers from the Department of Science and Technology (DOST), together with leaders from the Philippines Esports and Digital Innovation Sectors, as well as key stakeholders, held a collaboration meeting to discuss an upcoming nationwide event.',
    buttonText: 'Visit Website',
    buttonLink: 'https://newsphilippinesonline.com/newnews/index.php'
};

// 3. Theme Song Data
const themeSong = {
    image: '/assets/moa.jpg',
    imageAlt: 'Theme Song Image',
    title: 'Legends Rise in the MetaGames',
    artist: "Meta Games OST",
    lyrics: 'Experience the electrifying beats of the Official MetaGames Theme Song, a powerful anthem that captures the spirit of competition and camaraderie in the gaming world. This dynamic track is designed to energize players and fans alike, embodying the excitement and passion of esports. Whether you\'re gearing up for a tournament or just want to feel the thrill of gaming, the MetaGames Theme Song is your ultimate soundtrack for victory.',
    audio: 'Listen Now',
    parts: [
        {
            type: "Verse 1",
            lyrics: [
                "Here is where we carve our name this is more than just a game ",   
                "We level up with each new quest and prove ourselves as the very best."
            ]
        },
        {
            type: "Verse 2",
            lyrics: [
                
                "Our minds are sharp, our skills refined",
                "our passion for victory enshrined"
            ]
        }
    ]
};
</script>

<template>
    <header class="relative flex w-full max-w-380 min-h-60 md:min-h-70 my-8 mx-auto items-center rounded-3xl overflow-hidden px-6 md:px-16">
        <div class="absolute inset-0 z-0">
            <img
                :src="headerImage"
                alt="Hero Background"
                class="h-full w-full object-cover object-center" 
            />
            <div class="absolute inset-0 dark:bg-black/30 bg-black/10"></div>
        </div>

        <div class="relative z-10 flex flex-col justify-center max-w-2xl text-white text-left">
            <h1 class="text-3xl sm:text-4xl md:text-5xl font-bold mb-2 drop-shadow-lg">
                {{ title }}
            </h1>
            <p class="text-xl sm:text-2xl md:text-3xl font-semibold drop-shadow-lg text-gray-200">
                {{ subtitle }}
            </p>
        </div>
    </header>

    <section class="grid grid-cols-1 md:grid-cols-1 lg:grid-cols-2 gap-8 md:gap-12 max-w-400 mx-auto px-6 md:px-16 py-8 md:py-12 items-center">
        <figure class="w-full">
            <img 
                :src="article.image" 
                :alt="article.imageAlt"
                class="w-full h-auto rounded-3xl object-cover shadow-lg"
            >
        </figure>

        <article class="flex flex-col items-start gap-4 md:gap-6 w-full overflow-hidden">
            <h2 class="text-[#137DC1] text-xl sm:text-2xl md:text-2xl lg:text-3xl font-bold leading-snug max-w-3xl break-words text-balance">
                {{ article.title }}
            </h2>
            
            <p class="text-gray-800 dark:text-gray-300 text-base md:text-lg leading-relaxed">
                {{ article.content }}
            </p>

            <a 
                :href="article.buttonLink" 
                target="_blank"
                rel="noopener noreferrer"
                class="inline-flex items-center gap-2 bg-[#137DC1] text-white text-base md:text-lg font-semibold px-8 py-3 rounded-xl hover:bg-[#4089f7] transition-colors duration-300 shadow-md hover:shadow-lg mt-2"
            >
                {{ article.buttonText }}
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                    <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                </svg>
            </a>
        </article>
    </section>

    <div class="flex p-6 text-center text-4xl md:text-5xl font-semibold text-[#137DC1] justify-center">
        Official MetaGames Theme Song
    </div>

    <section class="grid grid-cols-1 md:grid-cols-1 lg:grid-cols-2 gap-8 md:gap-12 max-w-400 mx-auto px-6 md:px-16 py-8 md:py-12 items-start">
        
        <figure class="w-full">
            <img 
                :src="themeSong.image" 
                :alt="themeSong.imageAlt"
                class="w-full h-auto rounded-3xl object-cover shadow-lg"
            >
        </figure>
       
        <article class="flex flex-col w-full h-full">
            <header class="mb-4">
                <h1 class="text-2xl md:text-3xl font-bold">"{{ themeSong.title }}"</h1>
                <h2 class="text-xl md:text-2xl font-semibold dark:text-gray-300">{{ themeSong.artist }}</h2>
            </header>

           <div class="custom-scrollbar overflow-y-auto max-h-64 pr-4 space-y-6 text-gray-800 dark:text-gray-300 rounded-lg">
        <section v-for="(part, index) in themeSong.parts" :key="index">
            <h3 class="font-bold text-2xl mb-1 text-gray-900 dark:text-white">
                {{ part.type }}
            </h3>
            <p class="leading-relaxed text-xl">
                <span v-for="(line, i) in part.lyrics" :key="i">
                    {{ line }}<br>
                </span>
            </p>
        </section>
    </div>
        </article>
    </section>
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
        scrollbar-color: #2465c0 transparent; /* Tailwind gray-600 */
    }
    .custom-scrollbar::-webkit-scrollbar-thumb {
        background-color: #006aff; 
    }
}
</style>
