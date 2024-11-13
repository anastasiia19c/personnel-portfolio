<template>
  <div
    class="
      container
      mx-auto
      flex flex-col-reverse
      md:flex-row
      py-5
      md:py-10 md:mt-10
    "
  >
    <!-- Contact details -->
    <ContactDetails :contacts="contacts" />
  </div>
</template>

<script>
  import feather from "feather-icons";
  import ContactDetails from "@/components/contact/ContactDetails.vue";

  export default {
    components: {
      ContactDetails,
    },
    data() {
      return {
        contacts: [
          {
            id: 1,
            name: "atatkova04@gmail.com",
            icon: "mail",
          },
          {
            id: 2,
            name: "+33 7 49 02 52 43",
            icon: "phone",
          },
        ],
      };
    },
    mounted() {
      feather.replace();
    },
    updated() {
      feather.replace();
    },
    methods: {},
  };
</script>

