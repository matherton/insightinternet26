<template>
  <v-app-bar :elevation="2">
    <!--  <template v-slot:prepend>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
    </template> -->

    <v-app-bar-title @click="toTop()" style="cursor: pointer">
      InsightInternet
    </v-app-bar-title>

    <v-btn
      color="primary"
      class="ma-2"
      @click="scrollToAboutSection()"
      variant="elevated"
    >
      About
    </v-btn>
    <v-btn
      color="primary"
      class="ma-2"
      @click="scrollToSolutionsSection()"
      variant="elevated"
    >
      Solutions
    </v-btn>
    <v-btn
      color="primary"
      class="ma-2"
      @click="scrollToWorkSection()"
      variant="elevated"
    >
      Work
    </v-btn>
    <v-btn
      color="primary"
      class="ma-2"
      @click="scrollToContactSection()"
      variant="elevated"
    >
      Contact
    </v-btn>

    <!-- <template v-slot:append>
      <v-btn icon="mdi-heart"></v-btn>

      <v-btn icon="mdi-magnify"></v-btn>

      <v-btn icon="mdi-dots-vertical"></v-btn>
    </template> -->
  </v-app-bar>
</template>

<script>
export default {
  methods: {
    scrollToAboutSection() {
      const aboutSection = document.getElementById("about-section");
      aboutSection.scrollIntoView({ behavior: "smooth" });
    },
    scrollToSolutionsSection() {
      const solutionsSection = document.getElementById("solutions-section");
      solutionsSection.scrollIntoView({ behavior: "smooth" });
    },
    scrollToWorkSection() {
      const workSection = document.getElementById("work-section");
      workSection.scrollIntoView({ behavior: "smooth" });
    },
    scrollToContactSection() {
      const contactSection = document.getElementById("contact-section");
      contactSection.scrollIntoView({ behavior: "smooth" });
    },
    toTop() {
      const top = document.getElementById("top");
      top.scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>
<script setup>
const links = [
  {
    href: "https://vuetifyjs.com/",
    icon: "mdi-information-outline",
    subtitle: "Learn about all InsightInternet History and ethos.",
    title: "About",
  },
  {
    href: "https://vuetifyjs.com/introduction/why-vuetify/#feature-guides",
    icon: "mdi-briefcase-outline",
    subtitle: "Explore frameworks and Tools.",
    title: "Solutions",
  },
  {
    href: "https://vuetifyjs.com/components/all",
    icon: "mdi-briefcase-account-outline",
    subtitle: "Discover what projects have been built by InsightInternet.",
    title: "Work",
  },
  {
    href: "https://discord.vuetifyjs.com",
    icon: "mdi-email-outline",
    subtitle: "Connect with InsightInternet.",
    title: "Contact",
  },
];
</script>
