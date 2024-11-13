<template>
  <div class="container mx-auto">
    <!-- Banner -->
    <AppBanner class="mb-5 sm:mb-8" />

    <!-- Projects -->
    <ProjectsGrid />

    <!-- Load more projects button -->
    <div class="mt-10 sm:mt-20 flex justify-center">
      <router-link
        to="/projects"
        class="
          font-general-medium
          flex
          items-center
          px-6
          py-3
          rounded-lg
          shadow-lg
          hover:shadow-xl
          bg-amber-400
          dark:bg-amber-400
          hover:bg-amber-200
          dark:hover:bg-amber-200
          focus:ring-1 focus:ring-rose-600
          text-gray-700
          dark:text-gray-700
          text-lg
          sm:text-xl
          duration-300
        "
        aria-label="More Projects"
      >
        <Button title="More Projects" />
      </router-link>
    </div>
  </div>
</template>

<script>
  import AppBanner from "@/components/shared/AppBanner";
  import ProjectsGrid from "../components/projects/ProjectsGrid.vue";
  import Button from "../components/reusable/Button.vue";

  export default {
    name: "Home",
    components: {
      AppBanner,
      ProjectsGrid,
      Button,
    },
  };
</script>


<style scoped></style>
