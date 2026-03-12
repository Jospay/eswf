<script setup lang="ts">
const brandIdentity = {
  title: '"META"',
  tagline: 'is a prefix meaning Beyond.',
  paragraphs: `The <strong>MetaMovement</strong> embraces all gaming genres and all digitalized traditional sports as “MetaSports”.`,
  primaryLogo: '/assets/partnersmeta.png',
  secondaryLogo: '/assets/partnerseswf.png' 
}
</script>

<template>
  <section class="w-full overflow-hidden">
    <header class="fade-in-up relative z-30 flex w-full items-center justify-center">
      <div class="h-2 flex-1 bg-[#137DC1] transition-all duration-300 sm:h-4 md:h-6 lg:h-8"></div>
      <h1 class="whitespace-nowrap bg-transparent px-4 text-center text-xl font-semibold text-[#137DC1] sm:px-6 sm:py-3 sm:text-2xl md:text-4xl">
        Partners
      </h1>
      <div class="h-2 flex-1 bg-[#137DC1] transition-all duration-300 sm:h-4 md:h-6 lg:h-8"></div>
    </header>

    <div class="fade-in-up mt-8 flex w-full flex-col items-center justify-center gap-4 px-4 text-center">
      <h2 class="text-2xl font-bold text-[#137DC1] sm:text-3xl md:text-4xl">
        {{ brandIdentity.title }}
      </h2>
      <p class="text-lg font-medium text-gray-800 dark:text-gray-200">
        {{ brandIdentity.tagline }}
      </p>
      <p 
        class="max-w-2xl text-base text-gray-800 dark:text-gray-200" 
        v-html="brandIdentity.paragraphs"
      ></p>
    </div>

    <div class="fade-in-up my-10 flex w-full flex-row flex-wrap items-center justify-center gap-8 px-4 sm:gap-16">
      <img :src="brandIdentity.primaryLogo" alt="Meta Primary Logo" class="h-20 w-auto object-contain sm:h-28 md:h-32" />
      <img :src="brandIdentity.secondaryLogo" alt="Meta Secondary Logo" class="h-20 w-auto object-contain sm:h-28 md:h-32" />
    </div>

  </section>
</template>

<style scoped>
.fade-in-up {
  opacity: 0;
  animation: fadeInUp 0.6s ease-out forwards;
}
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>