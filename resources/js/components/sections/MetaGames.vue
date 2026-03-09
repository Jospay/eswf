<script setup lang="ts">
// Define your standard data here
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


    <div class="relative z-10 flex items-center justify-center w-full max-w-7xl mx-auto mt-8 mb-12 px-4 sm:px-6">
        
        <img 
          :src="bannerData.images.background" 
          alt="ESWF Anniversary Background" 
          class="w-full h-auto object-cover rounded-3xl max-h-[60vh] md:max-h-[85vh]"
        >
  
        
    </div>
  </section>
</template>