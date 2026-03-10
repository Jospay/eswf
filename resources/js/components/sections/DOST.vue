<script setup lang="ts">
import { ref } from 'vue';

const article = {
    title: `DOST - Regional Operations`,
    paragraphs: [
        `CHECK THIS OUT | DOST, ESWF collaborate to revolutionize Gaming Industry and Digital Sports in the Philippines`,
        `The Department of Science and Technology (DOST), in partnership with the eSports World Federation (ESWF), will officially tie its partnership through a Ceremonial Memorandum of Understanding Signing to support the growth and development of the gaming industry and digital sports in the country on February 19, 2024.`,
        `The partnership commits to collaborative programs, projects, and activities that support the gaming industry by tapping local talents in the creation and development of digital games and digital sports that support educational, cultural, and S&T-based digital games and digital sports in its sixteen (16) DOST regions and partner LGUs and SUCs, and towards the promotion of the same by jointly organizing events, conferences, seminars, and training programs, and the conduct of yearly regional and national exhibits and competitions.`,
        `Moreover, the alliance will implement training programs, workshops, and seminars to equip and nurture aspiring inventors with the necessary skills and knowledge to promote and market Filipino-developed digital games. This is also one of the initiatives of the government to attract foreign investments and foster a vibrant innovation ecosystem within the Philippine gaming sector.`,
        `Become a part of our pursuit of Filipino creativity in digital games and esports and help us revolutionize the Philippine digital sport and gaming industry by creating limitless possibilities for local developers, esports competitors, and other stakeholders.`,
    ],
    gridImages: [
        '/assets/dost1.jpg',
        '/assets/dost2.jpg',
        '/assets/dost3.jpg',
        '/assets/dost4.jpg'
    ],
    actionLink: 'https://infinityesportslatam.com/',
    actionText: 'infinityesportslatam.com'
};

const ewfLeader = {
    title: `Esports World Federation leaders touch base with PSC`,
    paragraphs: [
        'MANILA, Philippines – Officials and representatives of the Esports World Federation and General Association of World Sports Federations Macau China paid a courtesy call to Philippine Sports Commission (PSC) Chairman Richard Bachmann on Monday.',
        'In the photo (from left) are PSC Commissioner Walter Torres; Esports World Federation Chairman and Asian Television content Corporation CEO Engr. Reynaldo Sanchez; former Pagcor Gaming Department head Reynaldo De Guzman; General Association of World Sports Federations Macau China Chairman and President World Sports University  Dr. Che Kuong Hon and Esports World Federation Founder and President Arniel Gutierrez.',
        'PSC Bldg October 16, 2023'
    ],
    image: '/assets/psc.jpg',
    imageAlt: 'Philippine Sports Commission',
    links: [
        {
            text: 'Philstar.com',
            url: 'https://www.philstar.com/sports/2023/10/17/2304502/esports-world-federation-leaders-touch-base-psc?fbclid=IwAR0eZWgKkZmJ5uZSgSXauKJmoZ3gzV8AeFth36AX5PpqwfhwjVlMmCmCCPI',
            bgColor: 'bg-[#137DC1]',
            hoverColor: 'hover:bg-[#4089f7]',
            textColor: 'text-white'
        },
        {
            text: 'Metropoler.net',
            url: 'https://www.philstar.com/sports/2023/10/17/2304502/esports-world-federation-leaders-touch-base-psc?fbclid=IwAR0eZWgKkZmJ5uZSgSXauKJmoZ3gzV8AeFth36AX5PpqwfhwjVlMmCmCCPI', 
            bgColor: 'bg-[#FBD408]',
            hoverColor: 'hover:bg-[#e5c107]', 
            textColor: 'text-gray-800'
        }
    ]
}

const isExpanded = ref(false);

const toggleReadMore = () => {
    isExpanded.value = !isExpanded.value;
};
</script>

<template>
    <section class="w-full overflow-hidden sm:overflow-visible px-4 py-8 sm:px-6 md:py-12 lg:px-8">
        
        <div class="mx-auto flex max-w-7xl flex-col items-center">
            <h1 class="mb-6 text-center text-2xl font-semibold text-[#137DC1] sm:text-3xl md:text-4xl lg:text-5xl">
                {{ article.title }}
            </h1>

            <div class="flex flex-col gap-4 text-center">
                <p
                    v-for="(paragraph, index) in article.paragraphs"
                    :key="index"
                    v-show="index < 2 || isExpanded"
                    class="text-base leading-relaxed text-gray-900 transition-all duration-500 md:text-lg dark:text-gray-300"
                >
                    {{ paragraph }}
                </p>
            </div>

            <div class="mt-6 flex flex-wrap justify-center gap-x-6 gap-y-2 text-sm font-semibold text-[#137DC1] md:text-base">
                <p>#OneDOST4U</p> 
                <p>@Followers</p>
                <p>February 7, 2024</p>
            </div>

            <button
                @click="toggleReadMore"
                class="mt-8 inline-flex cursor-pointer items-center gap-2 rounded-xl bg-[#137DC1] px-12 py-3 text-base font-semibold text-white shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] hover:shadow-lg md:text-lg"
            >
                {{ isExpanded ? 'See less' : 'See All' }}
            </button>
        </div>

        <div class="mx-auto mt-16 w-full max-w-6xl">
            <div class="grid grid-cols-1 gap-8 sm:grid-cols-2 sm:gap-12">
                <div 
                    v-for="(imgSrc, index) in article.gridImages" 
                    :key="index"
                    class="overflow-hidden rounded-2xl shadow-md transition-all duration-300 hover:shadow-xl"
                >
                    <img 
                        :src="imgSrc" 
                        alt="DOST Operations Image" 
                        class="h-full w-full object-cover transition-transform duration-500 hover:scale-105"
                        loading="lazy"
                    />
                </div>
            </div>
        </div>

        <div class="mt-12 flex justify-center pb-8">
            <a
                :href="article.actionLink"
                target="_blank"
                rel="noopener noreferrer"
                class="inline-flex items-center gap-2 rounded-xl bg-[#1BAF6B] px-8 py-3.5 text-base font-medium text-white transition-all duration-300 hover:-translate-y-1 hover:bg-[#3bdd92] md:text-lg"
            >
                {{ article.actionText }}
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                    <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                </svg>
            </a>
        </div>

        <div class="mx-auto flex max-w-7xl flex-col items-center mt-12">
            <h1 class="mb-6 text-center text-2xl font-semibold text-[#137DC1] sm:text-3xl md:text-4xl lg:text-5xl">
                {{ ewfLeader.title }}
            </h1>

            <div class="flex flex-col gap-4 text-center">
                <p
                    v-for="(paragraph, index) in ewfLeader.paragraphs"
                    :key="index"
                    class="text-base leading-relaxed text-gray-900 transition-all duration-500 md:text-lg dark:text-gray-300"
                >
                    {{ paragraph }}
                </p>
            </div>
            
            <img 
                :src="ewfLeader.image" 
                :alt="ewfLeader.imageAlt" 
                class="mt-8 w-full max-w-4xl rounded-2xl shadow-lg object-cover"
                loading="lazy"
            />
            
            <div class="mt-8 flex flex-col sm:flex-row gap-4 sm:gap-6 w-full sm:w-auto justify-center">
                <a
                    v-for="(link, index) in ewfLeader.links"
                    :key="index"
                    :href="link.url"
                    target="_blank"
                    rel="noopener noreferrer"
                    :class="[
                        'inline-flex cursor-pointer items-center justify-center gap-2 rounded-xl px-8 py-3.5 text-base font-medium shadow-md transition-all duration-300 hover:-translate-y-1 hover:shadow-lg md:text-lg w-full sm:w-auto',
                        link.bgColor,
                        link.hoverColor,
                        link.textColor
                    ]"
                >
                    {{ link.text }}
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                        <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                    </svg>
                </a>
            </div>
        </div>
    </section>
</template>