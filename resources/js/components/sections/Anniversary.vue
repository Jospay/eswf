<script setup lang="ts">
const bannerData = {
  heading: {
    prefix: 'Happy',
    number: '7',
    suffix: 'th',
    title: 'Year ESWF'
  },
  subtitle: 'Connecting the World of Sports',
  dates: {
    start: {
      day: '26',
      monthYear: 'November 2018'
    },
    end: {
      day: '26',
      monthYear: 'November 2025'
    }
  },
  images: {
    background: '/assets/annivbg.jpg',
    overlay: '/assets/annivbg1.png'
  },
  metaimage: {
    first: '/assets/metamovement.png',
    second: '/assets/metasports.png',
    third: '/assets/metagames.png'
  }
}
</script>

<template>
  <section class="w-full overflow-hidden sm:overflow-visible">
    
    <header class="relative z-30 flex flex-col items-center justify-center p-6 mt-5 text-center text-white transition-colors bg-[#137DC1] dark:bg-[#137DC1]/50">
      <h1 class="text-2xl font-semibold sm:text-3xl md:text-4xl xl:text-5xl">
        {{ bannerData.heading.prefix }} {{ bannerData.heading.number }}<span class="text-sm align-super sm:text-base md:text-lg lg:text-xl">{{ bannerData.heading.suffix }}</span> {{ bannerData.heading.title }}
      </h1>
      <p class="mt-2 text-base font-medium break-normal sm:text-lg md:text-xl xl:text-4xl opacity-90">
        {{ bannerData.subtitle }}
      </p>
    </header>

    <div class="relative z-20 flex flex-col items-center justify-around w-full max-w-7xl mx-auto p-6 mt-5 text-[#137DC1] transition-colors dark:text-white sm:flex-row">
      <div class="w-full text-center sm:w-auto sm:text-left">
        <h2 class="font-semibold text-8xl md:text-9xl">{{ bannerData.dates.start.day }}</h2>
        <p class="text-2xl font-semibold md:text-3xl">{{ bannerData.dates.start.monthYear }}</p>
      </div>
      
      <div class="w-full mt-8 text-center sm:w-auto sm:mt-0 sm:text-right">
        <h2 class="font-semibold text-8xl md:text-9xl">{{ bannerData.dates.end.day }}</h2>
        <p class="text-2xl font-semibold md:text-3xl">{{ bannerData.dates.end.monthYear }}</p>
      </div>
    </div>

    <div class="relative z-10 flex items-center justify-center w-full max-w-7xl mx-auto mt-8 mb-12 px-4 sm:px-6">
        
        <img 
          :src="bannerData.images.background" 
          alt="ESWF Anniversary Background" 
          class="w-full h-auto object-cover rounded-3xl max-h-[60vh] md:max-h-[85vh]"
        >
        
        <img 
          :src="bannerData.images.overlay" 
          alt="ESWF Anniversary Overlay" 
          class="absolute left-1/2 transform -translate-x-1/2 -top-[40%] -bottom-[3%] h-[143%] w-auto max-w-[95vw] sm:max-w-none object-contain pointer-events-none drop-shadow-lg drop-shadow-gray-600 dark:drop-shadow-[0_10px_20px_rgba(255,255,255,0.25)]"
        >
        
    </div>

    <div class="flex flex-col sm:flex-row flex-wrap items-center justify-center w-full max-w-7xl mx-auto p-6 mt-5 text-[#137DC1] transition-colors dark:text-white gap-8 sm:gap-12">
      <img :src="bannerData.metaimage.first" alt="Meta Image 1" class="w-3/4 sm:w-auto max-w-50 md:max-w-62.5 h-auto object-contain">
      <img :src="bannerData.metaimage.second" alt="Meta Image 2" class="w-3/4 sm:w-auto max-w-50 md:max-w-62.5 h-auto object-contain">
      <img :src="bannerData.metaimage.third" alt="Meta Image 3" class="w-3/4 sm:w-auto max-w-50 md:max-w-62.5 h-auto object-contain">
    </div>

  </section>
</template>