<script setup lang="ts">
interface HeaderProps {
    headerImage?: string;
    title?: string;
}

const props = withDefaults(defineProps<HeaderProps>(), {
    headerImage: '/assets/policy.jpg',
    title: 'Policy making Bodies of Esports Genres Federations',
});

const profiles = [
    {
        name: 'Mark Hatter',
        role: 'President MMORPG',
        profilePicture: '/assets/p1.png',
        backGroundPicture: '/assets/p1.jpg',
        flag: '/assets/p1f.jpg',
        description: ''
    },
    {
        name: 'Arniel O. Gutierrez',
        role: 'President and Founder',
        profilePicture: '/assets/p2.png',
        backGroundPicture: '/assets/p2.jpg',
        flag: '/assets/p2f.jpg',
        description: ''
    },
    {
        name: 'Andy Koh',
        role: 'President',
        profilePicture: '/assets/p3.png',
        backGroundPicture: '/assets/p3.jpg',
        flag: '/assets/p3f.jpg',
        description: 'President Asia Pacific Electronic Sports Confederation'
    }
];
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
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
            
            <div 
                v-for="(person, index) in profiles" 
                :key="index" 
                class="relative flex flex-col w-full aspect-2/3 bg-white p-3 dark:bg-gray-800 shadow-lg hover:shadow-xl transition-shadow duration-300 border border-gray-100 dark:border-gray-700"
            >
                <div class="relative w-full aspect-square shadow-md shadow-blue-300 z-10 overflow-hidden shrink-0">
                    <img 
                        :src="person.backGroundPicture" 
                        alt="Background" 
                        class="w-full h-full object-cover" 
                    />
                    
                    <img 
                        :src="person.flag" 
                        alt="Country Flag" 
                        class="absolute top-3 right-3 w-8 h-6 object-cover rounded-[2px] shadow-sm border border-black/10" 
                    />
                </div>
                
                <div class="relative flex justify-center -mt-12 z-20 shrink-0">
                    <img 
                        :src="person.profilePicture" 
                        alt="Profile" 
                        class="w-24 h-24 rounded-full object-cover border-4 border-white dark:border-gray-800 bg-gray-100" 
                    />
                </div>

                <div class="flex flex-col items-center justify-center text-center px-4 pt-2 pb-6 grow rounded-b-2xl overflow-hidden z-0">
                    <h2 class="text-xl sm:text-lg lg:text-xl font-bold text-[#137DC1] dark:text-[#3da0e6] w-full truncate">
                        {{ person.name }}
                    </h2>
                    <p class="text-gray-900 dark:text-gray-300 text-sm font-medium mt-1 w-full truncate">
                        {{ person.role }}
                    </p>
                    <p v-if="person.description" class="text-gray-900 text-xs mt-2 line-clamp-2">
                        {{ person.description }}
                    </p>
                </div>
                
            </div>

        </div>
    </section>
</template>

<style scoped>
/* Scrollbar styles remain the same */
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
@media (prefers-color-scheme: dark) {
    .custom-scrollbar {
        scrollbar-color: #2465c0 transparent; 
    }
    .custom-scrollbar::-webkit-scrollbar-thumb {
        background-color: #006aff; 
    }
}
</style>