<script setup lang="ts">
import { computed } from 'vue';

const currentYear = computed(() => new Date().getFullYear());
</script>

<template>
  <footer class="w-full bg-[#137DC1] dark:bg-[#0B4A73] transition-colors duration-300">
    <div class="max-w-7xl mx-auto px-6 py-12 lg:py-16">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-10 lg:gap-8">
        
        <div class="flex flex-col space-y-6">
          <img 
            src="/assets/footerlogo.png" 
            class="h-20 w-auto object-contain object-left dark:brightness-110" 
            alt="Esports World Federation" 
          />
        </div>

        <div>
          <h3 class="text-sm font-bold text-white uppercase tracking-wider mb-4">Quick Links</h3>
          <ul class="space-y-3 text-sm font-medium text-blue-100 dark:text-blue-200">
            <li><a href="#home" class="hover:text-white hover:underline transition-all">Home</a></li>
            <li><a href="#news" class="hover:text-white hover:underline transition-all">News and Events</a></li>
            <li><a href="#dispute" class="hover:text-white hover:underline transition-all">Philippine Dispute Resolution Center</a></li>
            <li><a href="#cup" class="hover:text-white hover:underline transition-all">Continental & Regional Cup</a></li>
            <li><a href="#partners" class="hover:text-white hover:underline transition-all">Partners</a></li>
            <li><a href="#policy" class="hover:text-white hover:underline transition-all">Policy Making Bodies</a></li>
            <li><a href="#contact" class="hover:text-white hover:underline transition-all">Contact Us</a></li>
          </ul>
        </div>

        <div>
          <h3 class="text-sm font-bold text-white uppercase tracking-wider mb-4">Memberships</h3>
          <ul class="space-y-3 text-sm font-medium text-blue-100 dark:text-blue-200">
            <li><a href="#organizations" class="hover:text-white hover:underline transition-all">Organizations</a></li>
            <li><a href="#regular-members" class="hover:text-white hover:underline transition-all">Regular Members</a></li>
            <li><a href="#associate-members" class="hover:text-white hover:underline transition-all">Associate Members</a></li>
            <li><a href="#affiliate-members" class="hover:text-white hover:underline transition-all">Affiliate Members</a></li>
            <li><a href="#meta" class="hover:text-white hover:underline transition-all">Meta Movement</a></li>
          </ul>
        </div>

        <div>
          <h3 class="text-sm font-bold text-white uppercase tracking-wider mb-4">Initiatives & Depts</h3>
          <ul class="space-y-3 text-sm font-medium text-blue-100 dark:text-blue-200">
            <li><a href="#commissions" class="hover:text-white hover:underline transition-all">ESWF Commissions</a></li>
            <li><a href="#licenses" class="hover:text-white hover:underline transition-all">Licensing Department</a></li>
            <li><a href="#cares" class="hover:text-white hover:underline transition-all">ESFW Cares</a></li>
            <li><a href="#academy" class="hover:text-white hover:underline transition-all">Digital Sports Academy</a></li>
          </ul>
        </div>

      </div>
    </div>

    <div class="w-full bg-white dark:bg-neutral-800 text-[#137DC1] dark:text-white border-t border-gray-300 dark:border-transparent transition-colors duration-300">
      <div class="max-w-7xl mx-auto px-6 py-4 flex flex-col md:flex-row justify-between items-center gap-4 text-xs md:text-sm text-center md:text-left">
        <div>
          © {{ currentYear }} 
          <a href="/" class="font-semibold hover:underline transition-all dark:text-white">
            Esports World Federation
          </a>. 
          All Rights Reserved.
        </div>
        <div>
          Designed & Developed by 
          <a 
            class="font-semibold hover:underline transition-all dark:text-white" 
            href="https://bb88advertising.com/" 
            target="_blank" 
            rel="noopener noreferrer"
          >
            BB 88 Advertising and Digital Solutions Inc.
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>