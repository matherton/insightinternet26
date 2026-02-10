<template>
  <v-container class="fill-height d-flex align-center" max-width="900" id="top">
    <div>
      <v-img class="mb-4" height="250" src="../assets/me-cropped.png" />

      <div class="mb-8 text-center">
        <div class="text-body-2 font-weight-light mb-n1">Welcome to</div>
        <h1 class="text-h2 my-0 font-weight-bold">InsightInternet</h1>
        <h2 class="text-grey mb-2">
          Empowering Startups with Cutting-Edge Applications
        </h2>
        <p>
          At InsightInternet, we specialise in delivering high-quality
          applications to help startups succeed. Dedicated to providing bespoke
          solutions that drive growth and efficiency as well as delivering
          customised solutions without the constrants of cloud-based website
          builders i.e. Wix, Squarespace ect.
        </p>
      </div>

      <v-row>
        <v-col v-for="link in links" :key="link.href" cols="6">
          <v-card
            append-icon="mdi-open-in-new"
            class="py-4"
            color="surface-variant"
            :prepend-icon="link.icon"
            rel="noopener noreferrer"
            rounded="lg"
            :subtitle="link.subtitle"
            target="_blank"
            :title="link.title"
            variant="tonal"
          />
        </v-col>

        <v-col cols="12">
          <v-card
            class="py-4"
            href="#contact"
            color="surface-variant"
            image="https://cdn.vuetifyjs.com/docs/images/one/create/feature.png"
            prepend-icon="mdi-rocket-launch-outline"
            rounded="lg"
            variant="tonal"
          >
            <template #image>
              <v-img position="top right" />
            </template>

            <template #title>
              <h2 class="text-h5 font-weight-bold">Get started</h2>
            </template>

            <template #subtitle>
              <div class="text-subtitle-1">
                Transform your business with custom-built solutions tailored to
                your needs.
              </div>
            </template>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      handleEvent: null, // Initialize with a default value
    };
  },
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
  },
};
</script>
<script setup>
const links = [
  {
    href: "https://vuetifyjs.com/",
    icon: "mdi-information-outline",
    subtitle:
      "InsightInternet was founded with a vision to support startups by providing top-notch applications. Based in Edinburgh and partnering with Edinburgh startups and small businesses, we leverage the latest technologies to create seamless, responsive, and scalable applications.",
    title: "Story",
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
