<script setup lang="ts">
const elevations = [
    { title: 'Front Side', image: '/assets/frontpage.jpg', color: 'from-[#1BAF6B]' },
    { title: 'Right Side', image: '/assets/rightside.jpg', color: 'from-[#137DC1]' },
    { title: 'Left Side', image: '/assets/leftside.jpg', color: 'from-[#FBD408]' },
    { title: 'Rear Side', image: '/assets/rearside.jpg', color: 'from-[#E94140]' },
];
</script>

<template>
    <div class="relative w-full bg-white dark:bg-neutral-800 p-8">
        
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
                <div :class="['absolute inset-0 pointer-events-none bg-linear-to-t via-transparent to-transparent', item.color]"></div>
                <div class="absolute inset-x-0 bottom-0 p-6 justify-center text-center">
                    <h3 class="text-2xl font-bold text-white drop-shadow-md">{{ item.title }}</h3>
                    <h3 class="text-2xl font-bold text-white drop-shadow-md">Elevation</h3>
                </div>
            </div>
        </div>
        
    </div>
</template>