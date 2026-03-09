<script setup lang="ts">
const elevations = [
    {
        title: 'Front Side',
        image: '/assets/frontpage.jpg',
        color: 'from-[#1BAF6B]',
    },
    {
        title: 'Right Side',
        image: '/assets/rightside.jpg',
        color: 'from-[#137DC1]',
    },
    {
        title: 'Left Side',
        image: '/assets/leftside.jpg',
        color: 'from-[#FBD408]',
    },
    {
        title: 'Rear Side',
        image: '/assets/rearside.jpg',
        color: 'from-[#E94140]',
    },
];
</script>

<template>
    <div class="relative w-full bg-white p-4 sm:p-8 dark:bg-neutral-800">
        
        <div class="mx-auto grid max-w-7xl grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-4">
            <div
                v-for="(item, index) in elevations"
                :key="index"
                class="group relative aspect-3/4 overflow-hidden rounded-2xl bg-neutral-800 shadow-2xl transition-all duration-500 hover:-translate-y-2"
            >
                <img
                    :src="item.image"
                    class="h-full w-full object-cover transition-transform duration-700"
                    alt="Card Image"
                />
                <div
                    :class="[
                        'pointer-events-none absolute inset-0 bg-linear-to-t via-transparent to-transparent',
                        item.color,
                    ]"
                ></div>
                <div class="absolute inset-x-0 bottom-0 justify-center p-6 text-center">
                    <h3 class="text-2xl font-bold text-white drop-shadow-md">
                        {{ item.title }}
                    </h3>
                    <h3 class="text-2xl font-bold text-white drop-shadow-md">
                        Elevation
                    </h3>
                </div>
            </div>
        </div>

        <div class="mx-auto mt-12 max-w-4xl space-y-8 px-4 text-center md:mt-16 md:space-y-10 lg:px-0">
            
            <h2 class="text-2xl font-bold leading-snug text-[#137DC1] sm:text-3xl md:text-4xl">
                Look: World Esports MOBA Headquarters Officially Opens at The Peak Central Tower in Parañaque City
            </h2>

            <div class="space-y-5 text-base font-medium text-gray-800 dark:text-gray-300 sm:text-lg md:text-xl lg:px-8">
                <p>
                    A global sports icon and the only eight-division world boxing
                    champion, Pacquiao’s remarkable career and dedication to excellence
                    reflect the very values that define the esports community,
                    discipline, perseverance, and passion.
                </p>
                <p>
                    “We are thrilled and honored to welcome Manny Pacquiao to the ESWF family,” said Gio Colmenares Director of the Esports World Federation. “His legacy as an athlete and humanitarian inspires millions around the world, and his involvement will help strengthen the bridge between traditional sports and esports.”
                </p>
                <p>
                    As ESWF’s Global Ambassador, Pacquiao will play a vital role in promoting esports as a platform for unity, talent development, and global cooperation, championing the next generation of esports athletes and enthusiasts.
                </p>
            </div>

            <div class="pt-4">
                <a
                    href="https://www.facebook.com/story.php?story_fbid=122176330376525176&id=61565755302140&rdid=HdXPfiWbgnKoeu39#"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center gap-2 rounded-xl bg-[#137DC1] px-8 py-3.5 text-sm font-semibold text-white shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] hover:shadow-lg sm:px-12 sm:text-base md:px-16 md:text-lg"
                >
                    Visit Website
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 sm:h-6 sm:w-6" viewBox="0 0 20 20" fill="currentColor">
                        <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                    </svg>
                </a>
            </div>

        </div>
    </div>
</template>