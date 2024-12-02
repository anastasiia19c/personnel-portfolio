<template>
  <section
    class="
      flex flex-col
      sm:justify-between
      items-center
      sm:flex-row
      mt-12
      sm:mt-10
    "
  >
    <!-- Banner left contents -->
    <div class="w-full md:w-1/3 text-left">
      <h1
        class="
          font-general-semibold
          text-3xl
          md:text-4xl
          xl:text-4xl
          text-center
          sm:text-left
          text-primary-dark
          dark:text-primary-light
          uppercase
        "
      >
        Hello World, I am TATKOVA Anastasiia
      </h1>
      <p
        class="
          font-general-medium
          mt-2
          text-lg
          sm:text-xl
          xl:text-2xl
          text-center
          sm:text-left
          leading-none
          text-gray-400
        "
      >
        A Full-Stack Developer
      </p>
      <div class="flex justify-center sm:block">
        <a
          download="CV 2024 TATKOVA ANASTASIIA.pdf"
          href="/files/CV 2024 TATKOVA ANASTASIIA.pdf"
          class="
            flex
            justify-center
            items-center
            w-36
            sm:w-48
            mt-12
            mb-6
            sm:mb-0
            text-lg
            dark:border-ternary-dark
            py-2.5
            sm:py-3
            shadow-lg
            rounded-lg
            bg-amber-400
            dark:bg-amber-400
            focus:ring-1 focus:ring-rose-600
            hover:bg-amber-200
            dark:hover:bg-amber-200
            text-gray-700
            dark:text-gray-700
            hover:text-white-500
            dark:hover:text-gray-700
            duration-500
          "
          aria-label="Download Resume"
        >
          <i
            data-feather="arrow-down-circle"
            class="ml-0 sm:ml-1 mr-2 sm:mr-3 w-5 sm:w-6 duration-100"
          ></i>
          <span class="text-sm sm:text-lg font-general-medium duration-100"
            >Download CV</span
          ></a
        >
      </div>
    </div>

    <!-- Banner right illustration -->
    <div class="w-full md:w-1/2 text-right float-right">
      <img
        v-if="theme === 'light'"
        src="@/assets/images/avatar2.png"
        alt="Developer"
      />
      <img v-else src="@/assets/images/avatar2.png" alt="Developer" />
    </div>
  </section>
</template>

<script>
  import feather from "feather-icons";

  export default {
    name: "AppBanner",
    data() {
      return {
        theme: "",
      };
    },
    created() {
      this.theme = localStorage.getItem("theme") || "light";
    },
    mounted() {
      feather.replace();
      this.theme = localStorage.getItem("theme") || "light";
    },
    updated() {
      feather.replace();
    },
    methods: {},
  };
</script>



<style scoped>
</style>
