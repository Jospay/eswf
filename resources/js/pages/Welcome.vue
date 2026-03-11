<script setup lang="ts">
import NavBar from '@/components/NavBar.vue';
import Anniversary from '@/components/sections/Anniversary.vue';
import DOST from '@/components/sections/DOST.vue';
import ESWFWorldCup from '@/components/sections/EswfWorldCup.vue';
import GamesAmusements from '@/components/sections/GamesAmusements.vue';
import Header from '@/components/sections/Header.vue';
import Headquarter from '@/components/sections/Headquarter.vue';
import Home from '@/components/sections/Home.vue';
import Licenses from '@/components/sections/Licenses.vue';
import MetaGames from '@/components/sections/MetaGames.vue';
import NewsEvent from '@/components/sections/NewsEvent.vue';
import PolicyMaking from '@/components/sections/PolicyMaking.vue';
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
        
        <div class="sticky w-full z-50 top-0">
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
        <NewsEvent />
        <Anniversary />
        
        <div class="2xl:pb-18 xl:pb-13 lg:pb-0"><Headquarter /></div>
        <GamesAmusements />
        <MetaGames />
        <DOST />
        <Licenses />
        <PolicyMaking />
        
    </div>
</template>