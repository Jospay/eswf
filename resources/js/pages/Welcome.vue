<script setup lang="ts">
import Header from '@/components/sections/Header.vue';
import NavBar from '@/components/NavBar.vue';
import Home from '@/components/sections/Home.vue';
import ESWFWorldCup from '@/components/sections/EswfWorldCup.vue';
import WorldFederation from '@/components/sections/WorldFederation.vue';

withDefaults(
    defineProps<{
        canRegister: boolean;
    }>(),
    {
        canRegister: true,
    },
);
</script>

<template>
    <div class="relative w-full">
        
        <div class="relative w-full z-30">
            <Header />
            
            <div class="absolute bottom-0 left-0 w-full translate-y-1/2 px-4 md:px-8 lg:px-12 z-20">
                <div class="max-w-screen-3xl mx-auto">
                    <NavBar />
                </div>
            </div>
        </div>
        
        <div class="relative z-10 w-full lg:pb-10 md:pb-0">
            <Home />
        </div>
        <ESWFWorldCup />
        <WorldFederation />
        
    </div>
</template>