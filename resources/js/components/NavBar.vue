<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)
const activeLink = ref('Home')

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const setActive = (linkName: string) => {
  activeLink.value = linkName
  isMenuOpen.value = false
}
</script>

<template>
  <nav class="relative bg-white w-full max-w-screen-3xl mx-auto rounded-2xl shadow-lg border border-neutral-100 transition-all duration-300 z-50">
    <div class="flex flex-nowrap items-center justify-between p-4">
      
      <div class="flex items-center overflow-hidden shrink">
        
        <a href="#" @click="setActive('Home')" :class="activeLink === 'Home' ? 'text-[#137DC1]' : 'text-heading'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 lg:max-w-25 lg:opacity-100 lg:px-2">
           Home
        </a>
        
        <a href="#" @click="setActive('News and Events')" :class="activeLink === 'News and Events' ? 'text-[#137DC1]' : 'text-heading'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 lg:max-w-50 lg:opacity-100 lg:ml-4 lg:px-2">
           News and Events
        </a>
        
        <a href="#" @click="setActive('Policy Making')" :class="activeLink === 'Policy Making' ? 'text-[#137DC1]' : 'text-heading'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 lg:max-w-125 lg:opacity-100 lg:ml-4 lg:px-2">
           Policy Making Bodies of Esports Genres Federations
        </a>
        
        <a href="#" @click="setActive('Continental Cup')" :class="activeLink === 'Continental Cup' ? 'text-[#137DC1]' : 'text-heading'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 min-[1150px]:max-w-100 min-[1150px]:opacity-100 min-[1150px]:ml-4 min-[1150px]:px-2">
           Continental and Regional Esports Cup
        </a>
        
        <a href="#" @click="setActive('Partners')" :class="activeLink === 'Partners' ? 'text-[#137DC1]' : 'text-heading'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 min-[1250px]:max-w-37.5 min-[1250px]:opacity-100 min-[1250px]:ml-4 min-[1250px]:px-2">
           Partners
        </a>
        
        <a href="#" @click="setActive('Dispute Center')" :class="activeLink === 'Dispute Center' ? 'text-[#137DC1]' : 'text-heading'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 min-[1450px]:max-w-100 min-[1450px]:opacity-100 min-[1450px]:ml-4 min-[1450px]:px-2">
           Philippine Dispute Resolution Center
        </a>
        
        <a href="#" @click="setActive('Contact Us')" :class="activeLink === 'Contact Us' ? 'text-[#137DC1]' : 'text-heading'" 
           class="block overflow-hidden whitespace-nowrap font-medium hover:text-[#137DC1] transition-all duration-500 ease-in-out max-w-0 opacity-0 ml-0 px-0 min-[1600px]:max-w-37.5 min-[1600px]:opacity-100 min-[1600px]:ml-4 min-[1600px]:px-2">
           Contact Us
        </a>
      </div>

      <div class="grow"></div>

      <button 
        @click="toggleMenu" 
        type="button" 
        class="shrink-0 inline-flex items-center p-2 w-10 h-10 justify-center rounded-lg hover:bg-neutral-100 focus:outline-none focus:ring-2 focus:ring-neutral-200 transition-colors" 
        aria-controls="navbar-menu" 
        :aria-expanded="isMenuOpen"
      >
        <span class="sr-only">Toggle menu</span>
        <img 
          src="/assets/menu.png" 
          alt="Menu" 
          class="w-6 h-6 object-contain transition-all duration-500 ease-in-out"
          :class="isMenuOpen ? 'transform:[rotateY(180deg)] scale-110 opacity-70' : 'transform:[rotateY(0deg)]'"
        />
      </button>
    </div>

    <transition name="menu-slide">
      <div v-show="isMenuOpen" id="navbar-menu" class="absolute top-full left-0 mt-2 w-full border border-neutral-100 bg-white rounded-2xl shadow-xl overflow-hidden max-h-[70vh] overflow-y-auto custom-scrollbar">
        <ul class="flex flex-col p-4 font-medium space-y-2">
          
          <li class="md:hidden block mb-2 px-2">
            <button class="w-full bg-[#137DC1] text-white text-sm font-medium py-2.5 rounded-2xl hover:bg-[#106ba6] shadow-sm transition-all duration-300">
              Become a Member
            </button>
          </li>
          <div class="md:hidden block h-px bg-neutral-100 my-2 mx-4"></div>
          
          <li class="lg:hidden block"><a href="#" @click="setActive('Home')" :class="activeLink === 'Home' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Home</a></li>
          <li class="lg:hidden block"><a href="#" @click="setActive('News and Events')" :class="activeLink === 'News and Events' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">News and Events</a></li>
          <li class="lg:hidden block"><a href="#" @click="setActive('Policy Making')" :class="activeLink === 'Policy Making' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Policy Making Bodies of Esports Genres Federations</a></li>
          
          <li class="hidden max-[1149px]:block"><a href="#" @click="setActive('Continental Cup')" :class="activeLink === 'Continental Cup' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Continental and Regional Esports Cup</a></li>
          <li class="hidden max-[1249px]:block"><a href="#" @click="setActive('Partners')" :class="activeLink === 'Partners' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Partners</a></li>
          <li class="hidden max-[1449px]:block"><a href="#" @click="setActive('Dispute Center')" :class="activeLink === 'Dispute Center' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Philippine Dispute Resolution Center</a></li>
          <li class="hidden max-[1599px]:block"><a href="#" @click="setActive('Contact Us')" :class="activeLink === 'Contact Us' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Contact Us</a></li>
          
          <li><a href="#" @click="setActive('Organizations')" :class="activeLink === 'Organizations' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Organizations</a></li>
          <li><a href="#" @click="setActive('Regular Members')" :class="activeLink === 'Regular Members' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Regular Members</a></li>
          <li><a href="#" @click="setActive('Associate Members')" :class="activeLink === 'Associate Members' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Associate Members</a></li>
          <li><a href="#" @click="setActive('Affiliate Members')" :class="activeLink === 'Affiliate Members' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Affiliate Members</a></li>
          <li><a href="#" @click="setActive('Meta Movement')" :class="activeLink === 'Meta Movement' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">Meta Movement</a></li>
          <li><a href="#" @click="setActive('ESWF Commisions')" :class="activeLink === 'ESWF Commisions' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">ESWF Commisions</a></li>
          <li><a href="#" @click="setActive('Licensing Dept')" :class="activeLink === 'Licensing Dept' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">ESWF Licensing Department</a></li>
          <li><a href="#" @click="setActive('ESFW Cares')" :class="activeLink === 'ESFW Cares' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">ESFW Cares</a></li>
          <li><a href="#" @click="setActive('Academy')" :class="activeLink === 'Academy' ? 'text-[#137DC1] bg-blue-50' : 'text-heading'" class="block py-2 px-4 hover:bg-neutral-50 rounded-lg transition-colors duration-300">World Esports & Digital sports Academy</a></li>
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
</style>