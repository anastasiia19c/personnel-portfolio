<template>
  <div class="flex flex-col md:flex-row items-center justify-center py-4">
    <div class="w-full md:w-1/3">
      <img src="@/assets/images/iconTravail.png" alt="Icon Travail" class="w-full h-auto" />
    </div>
    
    <div class="w-full md:w-2/3 text-left px-4 md:px-5">
      <p class="text-xl text-primary-dark font-general-medium dark:text-primary-light 
      mt-2 max-w-3xl mx-auto rounded-lg bg-primary-light dark:bg-primary-dark shadow-lg px-6 py-4" style="text-align: justify;">
        Hello ! Je m'appelle Anastasiia et je suis une développeuse web full-stack. Actuellement, je suis étudiante en licence professionnelle 
        en développement logiciel à l'Université de Haute-Alsace à Mulhouse. Je suis en deuxième année dans <a :href="uhaLink" target="_blank" class="px-1 rounded underline">la formation UHA 4.0</a>.
        N'hésitez pas à jeter un œil sur ma formation. 
        <br>

        J'ai commencé mon parcours dans le développement web depuis 2022, lorsque je me suis intéressée à la création de sites web. 
        Depuis, j'ai acquis une maîtrise de diverses technologies et je suis devenue passionnée par la création de solutions efficaces et 
        fonctionnelles pour les utilisateurs. Aujourd'hui, ce n'est plus simplement une question d'esthétique, je commence à analyser les 
        sites et applications de manière plus globale, comme si je les scannais du regard.
        <br>
        Mon objectif est de continuer à évoluer en tant que spécialiste, maîtriser de nouvelles technologies et créer des solutions 
        utiles pour les utilisateurs.
        <br>

        Je parle 4 langues : le français, l'anglais, le russe, l'ukrainien. J'aime me lancer des défis pour évoluer, 
        c'est un défi personnel pour voir jusqu'où je peux aller.  
      </p>
    </div>
  </div>

  <!-- Skills Section -->
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <article data-page="skills">
      <header>
        <div class="text-2xl font-bold text-primary-dark dark:text-primary-light mb-5 fadein-bot title-section flex items-center">
          <div class="h-[1px] w-10 bg-amber-200 md:w-20 aos-init aos-animate" data-aos="zoom-in-left"
            data-aos-duration="600"></div>
          &nbsp; Skills
        </div>
      </header>
      <!-- Conteneur aligné à droite -->
      <div class="flex justify-end">
        <button @click="showDropdown = !showDropdown" class="bg-amber-200 text-gray-700 px-4 py-2 rounded-lg font-medium">
          {{ selectedCategory || 'Choisir une catégorie' }}
        </button>
      </div>

      <!-- Menu déroulant -->
      <div class="relative mt-2">
        <ul v-show="showDropdown" class="absolute right-0 mt-2 w-48 bg-white rounded-lg shadow-lg py-1 text-gray-700 z-10">
          <li>
            <button class="block w-full text-left px-4 py-2 hover:bg-amber-100"
              :class="{ 'bg-amber-200': activeTab === 1 }" @click="selectCategory('Language/Framework', 1)">Language/Framework</button>
          </li>
          <li>
            <button class="block w-full text-left px-4 py-2 hover:bg-amber-100"
              :class="{ 'bg-amber-200': activeTab === 2 }" @click="selectCategory('Applications', 2)">Applications</button>
          </li>
          <li>
            <button class="block w-full text-left px-4 py-2 hover:bg-amber-100"
              :class="{ 'bg-amber-200': activeTab === 3 }" @click="selectCategory('OS', 3)">OS</button>
          </li>
        </ul>
      </div>
      <!-- Tech Stack Section -->
      <div>
        <!-- Skills List -->
        <div v-show="activeTab === 1">
          <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
            <div v-for="item in skills" :key="item.id">
              <div class="item-tech flex cursor-pointer items-center gap-2 rounded border border-amber-200 px-2 py-2 hover:bg-amber-200 hover:bg-opacity-10 md:gap-3 lg:px-3">
                <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                  <img :alt="item.name" loading="lazy" class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]"
                    :src="item.imageUrl">
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div class="tech font-medium text-primary-dark dark:text-primary-light text-secondary transition-all duration-300 translate-y-0">{{ item.name }}</div>
                  <div class="status-tech opacity-0 absolute mt-5 text-[10px] text-amber-200 transition-all duration-300 md:text-xs lg:text-sm">
                    {{ item.status }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-show="activeTab === 2">
          <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
            <div v-for="item in application" :key="item.id">
              <div class="item-tech flex cursor-pointer items-center gap-2 rounded border border-amber-200 px-2 py-2 hover:bg-amber-200 hover:bg-opacity-10 md:gap-3 lg:px-3">
                <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                  <img :alt="item.name" loading="lazy" class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]"
                    :src="item.imageUrl">
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div class="tech font-medium text-primary-dark dark:text-primary-light text-secondary transition-all duration-300 translate-y-0">{{ item.name }}</div>
                  <div class="status-tech opacity-0 absolute mt-5 text-[10px] text-amber-200 transition-all duration-300 md:text-xs lg:text-sm">
                    {{ item.status }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-show="activeTab === 3">
          <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
            <div v-for="item in oS" :key="item.id">
              <div class="item-tech flex cursor-pointer items-center gap-2 rounded border border-amber-200 px-2 py-2 hover:bg-amber-200 hover:bg-opacity-10 md:gap-3 lg:px-3">
                <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                  <img :alt="item.name" loading="lazy" class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]"
                    :src="item.imageUrl">
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div class="tech font-medium text-primary-dark dark:text-primary-light text-secondary transition-all duration-300 translate-y-0">{{ item.name }}</div>
                  <div class="status-tech opacity-0 absolute mt-5 text-[10px] text-amber-200 transition-all duration-300 md:text-xs lg:text-sm">
                    {{ item.status }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </article>
  </div>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        { id: 1, name: 'HTML', imageUrl: 'https://cdn-icons-png.flaticon.com/512/1051/1051277.png' },
        { id: 2, name: 'CSS', imageUrl: 'https://cdn-icons-png.flaticon.com/512/732/732190.png' },
        { id: 3, name: 'PHP', imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-php-2038871-1720084.png' },
        { id: 4, name: 'Javascript', imageUrl: 'https://cdn.icon-icons.com/icons2/2415/PNG/512/javascript_original_logo_icon_146455.png' },
        { id: 5, name: 'Laravel', imageUrl: 'https://cdn.worldvectorlogo.com/logos/laravel-2.svg' },
        { id: 6, name: 'Java', imageUrl: 'https://cdn-icons-png.flaticon.com/512/226/226777.png' },
        { id: 7, name: 'VueJS', imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-vue-282497.png?f=webp' },
        { id: 8, name: 'Django Python', imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1869px-Python-logo-notext.svg.png' },
        { id: 9, name: 'NodeJS', imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-node-js-1174925.png' },
        { id: 10, name: 'Tailwind', imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/d/d5/Tailwind_CSS_Logo.svg' },
        { id: 11, name: 'Angular', imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Angular_full_color_logo.svg/2048px-Angular_full_color_logo.svg.png' },
        { id: 12, name: 'SpringBoot', imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/7/79/Spring_Boot.svg/640px-Spring_Boot.svg.png' },
        { id: 15, name: 'MySQL', imageUrl: 'https://cdn-icons-png.flaticon.com/512/5968/5968313.png'},
        { id: 16, name: 'Symfony', imageUrl: 'https://static-00.iconduck.com/assets.00/symfony-icon-512x512-94lugehx.png'},
        { id: 17, name: 'React Native', imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1200px-React-icon.svg.png'},
      ],
      application: [
        { id: 1, name: 'GitLab', imageUrl: 'https://cdn.worldvectorlogo.com/logos/gitlab-3.svg'},    
        { id: 2, name: 'GitHub', imageUrl: 'https://cdn-icons-png.flaticon.com/512/25/25231.png'},
        { id: 3, name: 'Postman', imageUrl: 'https://cdn.worldvectorlogo.com/logos/postman.svg'},
        { id: 4, name: 'Confluence', imageUrl: 'https://cdn.worldvectorlogo.com/logos/confluence-1.svg'},
        { id: 5, name: 'Jira', imageUrl: 'https://cdn.worldvectorlogo.com/logos/jira-3.svg'},
        { id: 6, name: 'Office 365', imageUrl: 'https://www.logo.wine/a/logo/Office_365/Office_365-Logo.wine.svg'},
      ],
      oS: [
        { id: 1, name: 'Linux', imageUrl: 'https://logo-marque.com/wp-content/uploads/2020/09/Linux-Logo-650x366.png'},    
        { id: 2, name: 'Windows', imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Windows_logo_-_2012.svg/1024px-Windows_logo_-_2012.svg.png'},
      ],
      showDropdown: false,
      activeTab: null,
      selectedCategory: '',
      uhaLink: "https://www.uha4point0.fr/licence-professionnelle-metier-de-l-informatique/" 
    };
  },
  methods: {
  selectCategory(category, tab) {
    this.selectedCategory = category;
    this.activeTab = tab;
    this.showDropdown = false;
    }
  }
};
</script>

<style lang="css" scoped>
.timeline-img {
  @apply h-24 w-24 object-cover rounded-full shadow-md border-4 
    border-secondary-light dark:border-secondary-dark 
    xs:absolute md:mx-auto md:left-0 md:right-0;
}

.timeline-container {
  @apply relative pt-2 xs:pl-28 xs:pt-0 md:w-1/2 md:ml-auto md:pl-16;
}

.timeline-container-left {
  @apply md:ml-0 md:mr-auto md:pl-0 md:pr-16;
}

.timeline-pointer {
  @apply absolute inset-0 left-10 h-4 w-4 transform rotate-45
    bg-neutral-100 dark:bg-secondary-dark
    border-neutral-100 dark:border-secondary-dark 
    xs:top-11 xs:left-26 md:left-14;
}

.timeline-pointer-left {
  @apply md:left-auto md:right-14;
}
</style>
