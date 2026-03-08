<script setup lang="ts">
import { onMounted } from 'vue';

declare let $: any;

interface EsportItem {
  id: number;
  title: string;
  description: string;
  imageUrl: string;
}

// 1. Static items for the first section (World Federation)
const worldItems: EsportItem[] = [
  { id: 1, title: "First Person Shooter", description: "FPS Esports World Cup 2026", imageUrl: "/assets/wfps.png" },
  { id: 2, title: "Fighting Games", description: "FG Esports World Cup 2026", imageUrl: "/assets/wfg.png" },
  { id: 3, title: "Real-Time Strategy", description: "RTS Esports World Cup 2026", imageUrl: "/assets/wrts.png" },
];

// 2. New sample data for the Carousel (International Federation)
const carouselItems: EsportItem[] = [
  { id: 101, title: "Multiplayer Online Battle Arena", description: "MOBA Esports World Cup 2026", imageUrl: "/assets/imoba.png" },
  { id: 102, title: "Battle Royale", description: "BR Esports World Cup 2026", imageUrl: "/assets/ibr.png" },
  { id: 103, title: "Massively Multiplayer Online Role-Playing Game", description: "MMORPG Esports World Cup 2026", imageUrl: "/assets/immorpg.png" },
  { id: 104, title: "Puzzle & Mind Games", description: "PMG Esports World Cup 2026", imageUrl: "/assets/ipmg.png" },
  { id: 105, title: "Rhythm Games", description: "RG Esports World Cup 2026", imageUrl: "/assets/irg.png" },
  { id: 106, title: "Collectible Card Games", description: "CCG Esports World Cup 2026", imageUrl: "/assets/iccg.png" },
  { id: 107, title: "Sandbox & Survival", description: "SS Esports World Cup 2026", imageUrl: "/assets/irg.png" },

];

onMounted(() => {
  const owl = $('.owl-carousel');
  owl.owlCarousel({
    loop: true,
    margin: 20,
    nav: false,
    dots: false,
    autoplay: true, 
    autoplayTimeout: 3000,
    responsive: {
      0: { items: 1 },
      768: { items: 2 },
      1024: { items: 3 }
    }
  });

  $('.btn-prev').click(() => owl.trigger('prev.owl.carousel'));
  $('.btn-next').click(() => owl.trigger('next.owl.carousel'));
});
</script>

<template>
  <div class="w-full bg-white dark:bg-neutral-800 py-10">
    
    <div class="flex justify-center p-6 text-center text-5xl font-semibold text-[#137DC1]">
      World Federation of Esport
    </div>

    <div class="max-w-370 mx-auto grid grid-cols-1 md:grid-cols-3 gap-6 py-3 px-4">
      <div v-for="item in worldItems" :key="item.id" class="item-pill dark:bg-gray-800">
        <img :src="item.imageUrl" :alt="item.title" class="pill-img" />
        <div class="flex flex-col overflow-hidden">
          <h2 class="text-2xl font-bold text-[#137DC1] truncate">{{ item.title }}</h2>
          <p class="text-gray-900 dark:text-gray-300 text-lg line-clamp-1">{{ item.description }}</p>
        </div>
      </div>
    </div>

    <div class="flex justify-center p-6 text-center text-5xl font-semibold text-[#137DC1] mt-12">
      International Federation of Esport
    </div>

    <div class="relative max-w-400 mx-auto px-16">
      <button class="btn-prev absolute left-2 top-1/2 -translate-y-1/2 z-10 cursor-pointer">
        <img src="/assets/larrow.png" alt="Prev" class="w-12 h-12 hover:scale-110 transition" />
      </button>

      <div class="owl-carousel owl-theme">
        <div v-for="item in carouselItems" :key="item.id" class="item-pill flex! m-2 dark:bg-gray-800">
          <img :src="item.imageUrl" :alt="item.title" class="pill-img" />
          <div class="flex flex-col overflow-hidden">
            <h2 class="text-2xl font-bold text-[#137DC1] truncate">{{ item.title }}</h2>
            <p class="text-gray-900 dark:text-gray-300 text-lg line-clamp-1">{{ item.description }}</p>
          </div>
        </div>
      </div>

      <button class="btn-next absolute right-2 top-1/2 -translate-y-1/2 z-10 cursor-pointer">
        <img src="/assets/rarrow.png" alt="Next" class="w-12 h-12 hover:scale-110 transition" />
      </button>
    </div>

  </div>
</template>
<style scoped>
.item-pill {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.75rem;
  border-radius: 9999px;
  border-width: 1px;
  border-color: #eff6ff; /* blue-50 */
  box-shadow: 0 10px 15px -3px rgba(19, 125, 193, 0.4);
  transition: all 0.3s;
}

.pill-img {
  width: 5.5rem; /* w-22 */
  height: 5.5rem;
  border-radius: 9999px;
  object-fit: cover;
  flex-shrink: 0;
}

/* Fix Owl Carousel Image Override */
:deep(.owl-carousel .owl-item img) {
  width: 5.5rem !important;
  display: inline-block;
}
</style>