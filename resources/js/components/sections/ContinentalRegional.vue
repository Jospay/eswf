<script setup lang="ts">
const worldItems = [
  { id: 1, title: "Esports For all" },
  { id: 2, title: "Women’s Esports" },
  { id: 3, title: "Challenged (Person With Disabilities) Esports" },
];
</script>

<template>
  <section class="w-full bg-white py-8 dark:bg-neutral-800">
  <header
    class="relative z-30 mt-5 flex items-center justify-center bg-[#137DC1] p-6 text-center text-xl font-medium text-white transition-colors sm:text-2xl md:text-4xl dark:bg-[#137DC1]/50"
  >
    Continental And Regional Esports Cup
  </header>
  
    <div class="flex justify-center p-6 text-center text-4xl font-semibold text-[#137DC1]">
      ESWF World Cup Categories
    </div>
    
    <div class="mx-auto grid max-w-7xl grid-cols-1 gap-6 px-4 py-3 md:grid-cols-3">
      <div 
        v-for="item in worldItems" 
        :key="item.id" 
        class="flex flex-row items-center gap-4 rounded-xl bg-gray-50 p-4 shadow-sm dark:bg-gray-800"
      >
        <div class="flex h-16 w-16 shrink-0 items-center justify-center rounded-xl bg-[#137DC1] text-3xl font-bold text-white">
          {{ item.id }}
        </div>
        
        <div class="flex flex-col overflow-hidden">
          <h2 class="text-xl font-medium text-gray-900 md:text-2xl dark:text-white">
            {{ item.title }}
          </h2>
        </div>
      </div>
    </div>
  </section>
</template>