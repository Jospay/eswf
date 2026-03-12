<script setup lang="ts">
</script>

<template>
  <section class="w-full overflow-hidden py-5">
    <header class="fade-in-up relative z-30 my-5 flex w-full items-center justify-center">
      
      <div class="flex-1 h-2 sm:h-4 md:h-6 lg:h-8 bg-[#137DC1] transition-all duration-300"></div>
      
      <h1 class="whitespace-nowrap bg-transparent px-4 py-2 text-center text-xl font-semibold text-[#137DC1] sm:px-6 sm:py-3 sm:text-2xl md:text-4xl">
        Partners
      </h1>
      
      <div class="flex-1 h-2 sm:h-4 md:h-6 lg:h-8 bg-[#137DC1] transition-all duration-300"></div>
      
    </header>
  </section>
</template>

<style scoped>
.fade-in-up {
    opacity: 0;
    animation: fadeInUp 0.6s ease-out forwards;
}
@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}
</style>