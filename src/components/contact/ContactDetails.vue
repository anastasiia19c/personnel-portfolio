<template>
  <div class="w-full md:w-1/1">
    <div>
      <h2
        class="
          font-general-medium
          text-xl md:text-xl lg:text-xl
          text-primary-dark
          dark:text-primary-light
          mt-12
          mb-12
          max-w-3xl
          text-center
          mx-auto
          px-6
          py-4
          rounded-lg
          bg-primary-light
          dark:bg-primary-dark
          shadow-lg
        "
      >
        Pour toute proposition, collaboration ou question concernant mon parcours, 
        mes compétences ou un projet spécifique, je vous invite à me contacter par l’un des moyens suivants. 
        Je serai ravie d’échanger avec vous et de discuter de toute opportunité professionnelle, 
        d’idée de partenariat ou simplement de répondre à vos questions. N’hésitez pas à me joindre, 
        je suis disponible et ouverte à toute discussion. 
      </h2>
      <ul class="font-general-regular">
        <li class="flex" v-for="contact in contacts" :key="contact.id">
          <i
            :data-feather="contact.icon"
            class="w-5 text-gray-500 dark:text-gray-400 mr-4"
          ></i>
          <!-- Vérification si c'est un email ou un numéro -->
          <a
            :href="getContactHref(contact)"
            class="
              text-lg
              mb-4
              text-primary-dark
              dark:text-primary-light
              hover:underline
              cursor-pointer
            "
            :aria-label="contact.icon === 'mail' ? 'Email' : 'Phone'"
          >
            {{ contact.name }}
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactDetail",
  props: ["contacts"],
  methods: {
    // Fonction pour retourner le bon href selon l'icône
    getContactHref(contact) {
      if (contact.icon === "mail") {
        return `mailto:${contact.name}`; // Pour les emails
      } else if (contact.icon === "phone") {
        return `tel:${contact.name}`; // Pour les numéros de téléphone
      }
      return "#"; 
    },
  },
};
</script>
