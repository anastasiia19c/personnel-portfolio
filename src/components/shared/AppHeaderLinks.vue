<template>
  <!-- Header links -->
  <div
    :class="isOpen ? 'block' : 'hidden'"
    class="
      m-0
      sm:ml-4
      mt-5
      sm:mt-3 sm:flex
      p-5
      sm:p-0
      justify-center
      items-center
      shadow-lg
      sm:shadow-none
      bg-secondary-light
      dark:bg-secondary-dark
      rounded-lg
      transition-transform duration-300 transform
    "
  >
    <router-link
      to="/"
      class="
        font-general-medium
        block
        text-left text-2xl
        font-medium
        text-primary-dark
        dark:text-primary-light
        hover:text-amber-400
        dark:hover:text-cyan-100
        sm:mx-4
        mb-2
        sm:py-2
      "
      aria-label="Home"
      >Accueil</router-link
    >
    <router-link
      to="/projects"
      class="
        font-general-medium
        block
        text-left text-2xl
        font-medium
        text-primary-dark
        dark:text-primary-light
        hover:text-amber-400
        dark:hover:text-cyan-100
        sm:mx-4
        mb-2
        sm:py-2
        border-t-2
        pt-3
        sm:pt-2 sm:border-t-0
        border-secondary-light
        dark:border-secondary-dark
      "
      aria-label="Projects"
      >Projets</router-link
    >
    <router-link
      to="/about"
      class="
        font-general-medium
        block
        text-left text-2xl
        font-medium
        text-primary-dark
        dark:text-primary-light
        hover:text-amber-400
        dark:hover:text-cyan-100
        sm:mx-4
        mb-2
        sm:py-2
        border-t-2
        pt-3
        sm:pt-2 sm:border-t-0
        border-secondary-light
        dark:border-secondary-dark
      "
      aria-label="About Me"
      >À Propos</router-link
    >
    <router-link
      to="/contact"
      class="
        font-general-medium
        block
        text-left text-2xl
        font-medium
        text-primary-dark
        dark:text-primary-light
        hover:text-amber-400
        dark:hover:text-cyan-100
        sm:mx-4
        mb-2
        sm:py-2
        border-t-2
        pt-3
        sm:pt-2 sm:border-t-0
        border-secondary-light
        dark:border-secondary-dark
      "
      aria-label="Contact"
      >Contact</router-link
    >

    <div
      class="
        border-t-2
        pt-3
        sm:pt-0 sm:border-t-0
        border-secondary-light
        dark:border-secondary-dark
      "
    ></div>
  </div>
</template>

<script>
  export default {
    name: "AppHeaderLink",
    props: ["showModal", "isOpen"],
  };
</script>


<style scoped>
</style>
