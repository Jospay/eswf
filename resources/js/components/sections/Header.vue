<script setup lang="ts">
interface HeaderProps {
  leftImageUrl?: string;
  rightImageUrl?: string;
  title?: string;
}

const props = withDefaults(defineProps<HeaderProps>(), {
  leftImageUrl: '/assets/footerlogo.png',
  rightImageUrl: '/assets/migs nav logo.png',
  title: 'My Dashboard'
});
</script>

<template>
  <header class="flex items-center justify-between w-full px-12 py-6 bg-white border-b border-gray-200">
    <div class="shrink-0">
        <a href="https://www.eswf.games/">
      <img 
        :src="props.leftImageUrl" 
        alt="Brand Logo Left" 
        class="h-15 w-auto object-contain"
      />
    </a>
    </div>


    <div class="shrink-0">
        <a href="https://www.migsinc.com/">
      <img 
        :src="props.rightImageUrl" 
        alt="Brand Logo Right" 
        class="h-15 w-auto object-contain"
      />
    </a>
    </div>
  </header>
</template>

<style scoped>
header {
  min-height: 64px;
}
</style>