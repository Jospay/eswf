<script setup lang="ts">

const brandIdentity = {
  title: '"META"',
  tagline: 'is a prefix meaning Beyond.',
  paragraphs: `The <strong>MetaMovement</strong> embraces all gaming genres and all digitalized traditional sports as “MetaSports”.`,
  primaryLogo: '/assets/partnersmeta.png',
  secondaryLogo: '/assets/partnerseswf.png' 
}

const partners = [
  { image: '/assets/partners1.png', title: 'International Sport Network Organization (ISNO)', description: 'International Sport Network Organization (ISNO) is a non profit organization based in Switzerland aiming to assist its members around the world.', subtitle: 'The categories of the members are:', list: ['International Member', 'Continental Member', 'National Member', 'Club / Local Member'], links:'https://www.isnosport.org/'},
  { image: '/assets/partners2.png', title: 'General Association of World Sports Federations (GAWSF)', description: 'The General Association of World Sports Federations (GAWSF) is a non-profit international sports organisation that serves as an umbrella organisation for numerous international, continental, and national sports federations and organisations. It was incorporated on November 20, 2014, in Macau as an international organisation with legal personality and received approval from SportAccord to use the name SportAccord Asia-Pacific Headquarters. In 2018, the organisation changed its name to the General Association of Asia Pacific Sports Federations (GAAPSF), and on April 20, 2023, it changed its name once again to GAWSF. Currently, GAWSF has more than 360 international, continental, and national member federations and has signed cooperation agreements with several international organisations that are now partners of GAWSF. The organisation has established representative offices in China, Hungary, Italy, Kuwait, Thailand, Philippines, Laos, Hong Kong, and Macau, and its activities cover the world, including sports games, competitions, trainings, forums, and more. The primary aim of GAWSF is to promote and develop sports and sports activities on a global scale.', subtitle: '', list: [], links:'https://gaapsf.net/index.php/en/' },
  { image: '/assets/partners3.png', title: 'INTERNATIONAL DIGITAL GAMES COMMITTEE', description: 'IDGC is the digital gaming medium of traditional sports. The authority responsible for organizing the different Digitus Games. committed to develop, promote and regulate all worldwide initiatives in different forms and formats of digital sports.', subtitle: '', list: [], links:'https://www.facebook.com/digitusgames/?_rdc=2&_rdr#' },
  { image: '/assets/partners4.png', title: 'DEPARTMENT OF SCIENCE AND TECHNOLOGY', description: 'The Department of Science and Technology (DOST) is the premiere science and technology body in the Philippines charged with the twin mandate of providing central direction, leadership and coordination of all scientific and technological activities, and of formulating policies, programs and projects to support national development.', subtitle: '', list: [], links:'https://www.dost.gov.ph/' },

];
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
      <p class="text-xl font-medium text-gray-800 dark:text-gray-200">
        {{ brandIdentity.tagline }}
      </p>
      <p 
        class="max-w-2xl text-lg text-gray-800 dark:text-gray-200" 
        v-html="brandIdentity.paragraphs"
      ></p>
    </div>

    <div class="fade-in-up my-10 flex w-full flex-row flex-wrap items-center justify-center gap-8 px-4 sm:gap-16">
      <img :src="brandIdentity.primaryLogo" alt="Meta Primary Logo" class="h-20 w-auto object-contain sm:h-28 md:h-32" />
      <img :src="brandIdentity.secondaryLogo" alt="Meta Secondary Logo" class="h-20 w-auto object-contain sm:h-28 md:h-32" />
    </div>

    <div class="mx-auto max-w-7xl px-4 py-8">
      <div 
        v-for="(partner, index) in partners" 
        :key="index" 
        class="fade-in-up mb-16 flex w-full flex-col items-center justify-center gap-8 md:flex-row md:items-start"
        :style="{ animationDelay: `${index * 150}ms` }"
      >
        
        <div class="flex w-full flex-shrink-0 items-center justify-center md:w-1/3 lg:w-1/4">
          <img 
            :src="partner.image" 
            :alt="partner.title" 
            class="max-h-48 w-auto object-contain md:max-h-56" 
          />
        </div>

        <div class="flex w-full flex-col items-center text-center md:w-2/3 md:items-start md:text-left lg:w-3/4">
          <h3 class="mb-4 text-2xl font-bold text-[#137DC1] md:text-3xl">
            {{ partner.title }}
          </h3>
          <p class="mb-4 text-lg text-gray-800 text-justify dark:text-gray-300">
            {{ partner.description }}
          </p>
          
          <div v-if="partner.subtitle || partner.list.length > 0" class="mb-6 w-full">
            <h4 v-if="partner.subtitle" class="mb-2 text-lg font-semibold text-gray-800 dark:text-gray-200">
              {{ partner.subtitle }}
            </h4>
            <ul v-if="partner.list.length > 0" class="list-inside list-disc space-y-1 text-gray-800 dark:text-gray-300 md:ml-4">
              <li v-for="(item, i) in partner.list" :key="i">
                {{ item }}
              </li>
            </ul>
          </div>

          <div class="mt-2">
            <a 
              :href="partner.links" 
              target="_blank" 
              rel="noopener noreferrer" 
              class="inline-flex items-center justify-center gap-2 rounded-lg bg-yellow-400 px-8 py-2.5 text-sm font-semibold text-gray-900 shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-yellow-500"
            >
              View Website
            </a>
          </div>
        </div>

      </div>
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