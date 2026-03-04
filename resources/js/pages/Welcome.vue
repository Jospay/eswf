<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3';
import { dashboard, login, register } from '@/routes';
import Header from '@/components/sections/Header.vue';
import NavBar from '@/components/NavBar.vue';

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
        <Header />
        
        <div class="relative -mt-6 md:-mt-8 w-full z-20 px-4 md:px-8 lg:px-12 max-w-screen-3xl mx-auto">
            <NavBar />
        </div>
    </div>
</template>