<template>
  <v-app-bar :elevation="2">
    <v-app-bar-title @click="toTop()" style="cursor: pointer">
      InsightInternet
    </v-app-bar-title>

    <v-btn
      :size="buttonSize"
      color="primary"
      class="ma-0 ma-md-5"
      @click="scrollToAboutSection()"
      variant="elevated"
    >
      About
    </v-btn>
    <v-btn
      :size="buttonSize"
      color="primary"
      class="ma-0 ma-md-5"
      @click="scrollToSolutionsSection()"
      variant="elevated"
    >
      Solutions
    </v-btn>
    <v-btn
      :size="buttonSize"
      color="primary"
      class="ma-0 ma-md-5"
      @click="scrollToWorkSection()"
      variant="elevated"
    >
      Work
    </v-btn>
    <v-btn
      :size="buttonSize"
      color="primary"
      class="ma-0 ma-md-5"
      @click="scrollToContactSection()"
      variant="elevated"
    >
      Contact
    </v-btn>
  </v-app-bar>
</template>

<script setup>
import { computed } from "vue";
import { useDisplay } from "vuetify";

// useDisplay gives you live, reactive breakpoint info
const { xs, sm, lgAndUp } = useDisplay();

const buttonSize = computed(() => {
  if (xs.value) return "x-small";
  if (sm.value) return "small";
  if (lgAndUp.value) return "large";
  return "default";
});

function scrollTo(id) {
  document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
}

const scrollToAboutSection = () => scrollTo("about-section");
const scrollToSolutionsSection = () => scrollTo("solutions-section");
const scrollToWorkSection = () => scrollTo("work-section");
const scrollToContactSection = () => scrollTo("contact-section");
const toTop = () => scrollTo("top");
</script>
