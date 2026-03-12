<script setup lang="ts">
import { ref, onMounted } from 'vue'

const isMenuOpen = ref(false)
const activeLink = ref('Home')
const isDarkMode = ref(false)

// Sync initial dark mode state on load to prevent the double-click issue
onMounted(() => {
  if (
    document.documentElement.classList.contains('dark') ||
    window.matchMedia('(prefers-color-scheme: dark)').matches
  ) {
    isDarkMode.value = true
    document.documentElement.classList.add('dark')
  }
})

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

// Update state, close menu, and scroll to the correct section
const setActive = (linkName: string, sectionId: string) => {
  activeLink.value = linkName
  isMenuOpen.value = false
  
  const element = document.getElementById(sectionId)
  if (element) {
    // 100px offset to account for your sticky header so it doesn't cover the title
    const y = element.getBoundingClientRect().top + window.scrollY - 100 
    window.scrollTo({ top: y, behavior: 'smooth' })
  }
}

const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value
  
  if (isDarkMode.value) {
    document.documentElement.classList.add('dark')
  } else {
    document.documentElement.classList.remove('dark')
  }
}
</script>

<template>
  <nav class="relative bg-white dark:bg-neutral-900 w-full max-w-screen-3xl mx-auto rounded-2xl shadow-lg border border-neutral-100 dark:border-neutral-800 transition-all duration-300 z-50">
    
    <div class="flex flex-nowrap items-center w-full p-4">
      
      <div class="flex flex-1 items-center justify-center overflow-hidden shrink">
        
        <a href="#" @click.prevent="setActive('Home', 'home')" :class="activeLink === 'Home' ? 'text-[#137DC1]' : 'text-heading dark:text-gray-300'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] dark:hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 lg:max-w-25 lg:opacity-100 lg:px-2">
            Home
        </a>
        
        <a href="#" @click.prevent="setActive('News and Events', 'news')" :class="activeLink === 'News and Events' ? 'text-[#137DC1]' : 'text-heading dark:text-gray-300'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] dark:hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 lg:max-w-50 lg:opacity-100 lg:ml-4 lg:px-2">
            News and Events
        </a>
        
        <a href="#" @click.prevent="setActive('Dispute Center', 'dispute')" :class="activeLink === 'Dispute Center' ? 'text-[#137DC1]' : 'text-heading dark:text-gray-300'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] dark:hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 min-[1450px]:max-w-100 min-[1450px]:opacity-100 min-[1450px]:ml-4 min-[1450px]:px-2">
            Philippine Dispute Resolution Center
        </a>
        
        <a href="#" @click.prevent="setActive('Continental Cup', 'cup')" :class="activeLink === 'Continental Cup' ? 'text-[#137DC1]' : 'text-heading dark:text-gray-300'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] dark:hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 min-[1150px]:max-w-100 min-[1150px]:opacity-100 min-[1150px]:ml-4 min-[1150px]:px-2">
            Continental and Regional Esports Cup
        </a>
        
        <a href="#" @click.prevent="setActive('Partners', 'partners')" :class="activeLink === 'Partners' ? 'text-[#137DC1]' : 'text-heading dark:text-gray-300'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] dark:hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 min-[1250px]:max-w-37.5 min-[1250px]:opacity-100 min-[1250px]:ml-4 min-[1250px]:px-2">
            Partners
        </a>

        <a href="#" @click.prevent="setActive('Policy Making', 'policy')" :class="activeLink === 'Policy Making' ? 'text-[#137DC1]' : 'text-heading dark:text-gray-300'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] dark:hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 lg:max-w-125 lg:opacity-100 lg:ml-4 lg:px-2">
            Policy Making Bodies of Esports Genres Federations
        </a>
        
        <a href="#" @click.prevent="setActive('Contact Us', 'contact')" :class="activeLink === 'Contact Us' ? 'text-[#137DC1]' : 'text-heading dark:text-gray-300'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] dark:hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 min-[1600px]:max-w-37.5 min-[1600px]:opacity-100 min-[1600px]:ml-4 min-[1600px]:px-2">
            Contact Us
        </a>
      </div>

      <div class="flex items-center gap-1 sm:gap-2 shrink-0 ml-auto">
        <button 
          @click="toggleDarkMode" 
          type="button" 
          class="shrink-0 inline-flex items-center p-2 w-10 h-10 justify-center rounded-lg hover:bg-neutral-100 dark:hover:bg-neutral-800 focus:outline-none focus:ring-2 focus:ring-neutral-200 transition-colors" 
          aria-label="Toggle dark mode"
        >
          <svg v-if="isDarkMode" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-yellow-500 transition-transform duration-500 transform rotate-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z" />
          </svg>
          <svg v-else xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-neutral-600 dark:text-gray-300 transition-transform duration-500 transform -rotate-12" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z" />
          </svg>
        </button>

        <button 
          @click="toggleMenu" 
          type="button" 
          class="shrink-0 inline-flex items-center p-2 w-10 h-10 justify-center rounded-lg hover:bg-neutral-100 dark:hover:bg-neutral-800 focus:outline-none focus:ring-2 focus:ring-neutral-200 transition-colors" 
          aria-controls="navbar-menu" 
          :aria-expanded="isMenuOpen"
        >
          <span class="sr-only">Toggle menu</span>
          <img 
            src="/assets/menu.png" 
            alt="Menu" 
            class="w-6 h-6 object-contain transition-all duration-500 ease-in-out dark:invert dark:opacity-80"
            :class="isMenuOpen ? 'transform:[rotateY(180deg)] scale-110 opacity-70' : 'transform:[rotateY(0deg)]'"
          />
        </button>
      </div>
    </div>

    <transition name="menu-slide">
      <div v-show="isMenuOpen" id="navbar-menu" class="absolute top-full left-0 mt-2 w-full border border-neutral-100 dark:border-neutral-800 bg-white dark:bg-neutral-900 rounded-2xl shadow-xl overflow-hidden max-h-[70vh] overflow-y-auto custom-scrollbar">
        <ul class="flex flex-col p-4 font-medium space-y-2">
          
          <li class="md:hidden block mb-2 px-2">
            <button class="w-full bg-[#137DC1] text-white text-sm font-medium py-2.5 rounded-2xl hover:bg-[#106ba6] shadow-sm transition-all duration-300">
              Become a Member
            </button>
          </li>
          <div class="md:hidden block h-px bg-neutral-100 dark:bg-neutral-800 my-2 mx-4"></div>
          
          <li class="lg:hidden block"><a href="#" @click.prevent="setActive('Home', 'home')" :class="activeLink === 'Home' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Home</a></li>
          <li class="lg:hidden block"><a href="#" @click.prevent="setActive('News and Events', 'news')" :class="activeLink === 'News and Events' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">News and Events</a></li>
          <li class="lg:hidden block"><a href="#" @click.prevent="setActive('Dispute Center', 'dispute')" :class="activeLink === 'Dispute Center' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Philippine Dispute Resolution Center</a></li>
          
          <li class="hidden max-[1149px]:block"><a href="#" @click.prevent="setActive('Continental Cup', 'cup')" :class="activeLink === 'Continental Cup' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Continental and Regional Esports Cup</a></li>
          <li class="hidden max-[1249px]:block"><a href="#" @click.prevent="setActive('Partners', 'partners')" :class="activeLink === 'Partners' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Partners</a></li>
          <li class="hidden max-[1449px]:block"><a href="#" @click.prevent="setActive('Policy Making', 'policy')" :class="activeLink === 'Policy Making' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Policy Making Bodies of Esports Genres Federations</a></li>
          <li class="hidden max-[1599px]:block"><a href="#" @click.prevent="setActive('Contact Us', 'contact')" :class="activeLink === 'Contact Us' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Contact Us</a></li>
          
          <li><a href="#" @click.prevent="setActive('Organizations', 'organizations')" :class="activeLink === 'Organizations' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Organizations</a></li>
          <li><a href="#" @click.prevent="setActive('Regular Members', 'regular-members')" :class="activeLink === 'Regular Members' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Regular Members</a></li>
          <li><a href="#" @click.prevent="setActive('Associate Members', 'associate-members')" :class="activeLink === 'Associate Members' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Associate Members</a></li>
          <li><a href="#" @click.prevent="setActive('Affiliate Members', 'affiliate-members')" :class="activeLink === 'Affiliate Members' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Affiliate Members</a></li>
          <li><a href="#" @click.prevent="setActive('Meta Movement', 'meta')" :class="activeLink === 'Meta Movement' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">Meta Movement</a></li>
          <li><a href="#" @click.prevent="setActive('ESWF Commisions', 'commissions')" :class="activeLink === 'ESWF Commisions' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">ESWF Commisions</a></li>
          <li><a href="#" @click.prevent="setActive('Licensing Dept', 'licenses')" :class="activeLink === 'Licensing Dept' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">ESWF Licensing Department</a></li>
          <li><a href="#" @click.prevent="setActive('ESFW Cares', 'cares')" :class="activeLink === 'ESFW Cares' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">ESFW Cares</a></li>
          <li><a href="#" @click.prevent="setActive('Academy', 'academy')" :class="activeLink === 'Academy' ? 'text-[#137DC1] bg-blue-50 dark:bg-neutral-800' : 'text-heading dark:text-gray-300'" class="block py-2 px-4 hover:bg-neutral-50 dark:hover:bg-neutral-800 rounded-lg transition-colors duration-300">World Esports & Digital sports Academy</a></li>
        </ul>
      </div>
    </transition>
  </nav>
</template>

<style scoped>
.menu-slide-enter-active,
.menu-slide-leave-active {
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.menu-slide-enter-from,
.menu-slide-leave-to {
  opacity: 0;
  transform: translateY(-15px) scaleY(0.98);
}

.custom-scrollbar::-webkit-scrollbar {
  width: 6px;
}
.custom-scrollbar::-webkit-scrollbar-track {
  background: transparent;
}
.custom-scrollbar::-webkit-scrollbar-thumb {
  background-color: #d4d4d4;
  border-radius: 20px;
}
:global(.dark) .custom-scrollbar::-webkit-scrollbar-thumb {
  background-color: #525252;
}
</style>