<template>
  <!-- Projects grid -->
  <section class="pt-10 sm:pt-14">
    <!-- Projects grid title -->
    <div class="text-center">
      <p
        class="
          font-general-semibold
          text-4xl
          md:text-5xl
          font-semibold
          mb-12
          text-primary-dark
          dark:text-primary-light
        "
      >
        Projets
      </p>
    </div>

    <!-- Filter buttons -->
    <div class="text-center mb-6">
      <button
        @click="filter = 'all'"
        :class="{'bg-secondary-light dark:bg-secondary-dark text-primary-dark dark:text-primary-light': filter === 'all', 
                'dark:text-primary-light': filter !== 'all',
                'text-white': filter === 'all'}"
        class="px-4 py-2 mr-4 rounded"
      >
        Tous
      </button>
      <button
        @click="filter = 'solo'"
        :class="{'bg-secondary-light dark:bg-secondary-dark text-primary-dark dark:text-primary-light': filter === 'solo', 
                'dark:text-primary-light': filter !== 'solo',
                'text-white': filter === 'solo'}"
        class="px-4 py-2 mr-4 rounded"
      >
        Projets Solo
      </button>
      <button
        @click="filter = 'team'"
        :class="{'bg-secondary-light dark:bg-secondary-dark text-primary-dark dark:text-primary-light': filter === 'team',
                'dark:text-primary-light': filter !== 'team',
                'text-white': filter === 'team'}"
        class="px-4 py-2 rounded"
      >
        Projets d'Équipe
      </button>
    </div>

    <!-- Projects grid -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 mt-6 sm:gap-10">
      <ProjectCell
        v-for="project in filteredProjects" 
        :key="project.id"
        :project="project"
      />
    </div>
  </section>
</template>


<script>
  import feather from "feather-icons";
  import ProjectCell from "./ProjectCell.vue";
  import projectSummaries from "../../data/projectSummaries";

export default {
  name: "ProjectGrid",
  components: { ProjectCell },
  data() {
    return {
      filter: 'all', 
      projectSummaries: projectSummaries, 
    };
  },
  mounted() {
    feather.replace();
  },
  computed: {
    filteredProjects() {
      console.log("Filtre appliqué: ", this.filter);
      if (this.filter === 'all') {
        return this.projectSummaries; 
      }
      if (this.filter === 'solo') {
        return this.projectSummaries.filter(project => project.isSolo); 
      }
      if (this.filter === 'team') {
        return this.projectSummaries.filter(project => project.isTeam); 
      }
      return this.projectSummaries; 
    }
  }
};
</script>

