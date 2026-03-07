<script setup lang="ts">
interface HeaderProps {
    leftImageUrl?: string;
    rightImageUrl?: string;
    title?: string;
}

const props = withDefaults(defineProps<HeaderProps>(), {
    leftImageUrl: '/assets/footerlogo.png',
    rightImageUrl: '/assets/migs nav logo.png',
    title: 'My Dashboard',
});
</script>

<template>
    <header class="flex w-full gap-6 items-center bg-white dark:bg-neutral-800 px-4 md:px-8 lg:px-12 pt-6 md:pt-8 pb-10 md:pb-12 justify-center md:justify-between relative z-10">
        
        <div class="flex gap-3 sm:gap-4 md:gap-6 items-center">
            <div class="shrink-0">
                <a href="https://www.eswf.games/" class="block transition-transform hover:scale-105">
                    <img
                        :src="props.leftImageUrl"
                        alt="Brand Logo Left"
                        class="h-8 sm:h-10 md:h-12 lg:h-14 w-auto object-contain"
                    />
                </a>
            </div>
            <div class="shrink-0">
                <a href="https://www.migsinc.com/" class="block transition-transform hover:scale-105">
                    <img
                        :src="props.rightImageUrl"
                        alt="Brand Logo Right"
                        class="h-8 sm:h-10 md:h-12 lg:h-14 w-auto object-contain"
                    />
                </a>
            </div>
        </div>
        
        <div class="hidden md:block">
          <button class="bg-[#137DC1] text-white text-sm md:text-base font-medium px-5 md:px-6 py-2.5 rounded-2xl hover:bg-[#106ba6] shadow-sm hover:shadow-md transition-all duration-300 whitespace-nowrap">
              Become a Member
          </button>
        </div>

    </header>
</template>

<style scoped>
header {
    min-height: 64px;
}
</style>