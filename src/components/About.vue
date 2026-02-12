<script setup>
import List from "../utilities/List.vue";
import DynamicCard from "../utilities/DynamicCard.vue";
const items = [
  { text: "Real-Time", icon: "mdi-clock" },
  { text: "Audience", icon: "mdi-account" },
  { text: "Conversions", icon: "mdi-flag" },
];
</script>

<template>
  <v-divider
    color="primary"
    opacity=".7"
    thickness="10"
    variant="double"
    gradient
  >
    About
  </v-divider>
  <v-container>
    <v-row id="about-section" class="about" style="scroll-margin-top: 6rem">
      <v-col cols="12" md="4">
        <DynamicCard
          title="Story"
          text="InsightInternet was founded with a vision to support startups by providing top-notch applications. Based in Edinburgh and partnering with Edinburgh startups and small businesses, we leverage the latest technologies to create seamless, responsive, and scalable applications."
          variant="text"
        />
      </v-col>
      <!-- inline style above to ensure this header is not scrolled behind sticky nav bar -->
      <v-col cols="12" md="4">
        <List :items="items" />
      </v-col>

      <v-col cols="12" md="4">
        <DynamicCard
          title="Mission Statement"
          text="Our mission is to empower startups with robust and scalable applications, ensuring they have the technological edge to succeed in a competitive market Values Innovation Quality Collaboration Integrity"
          variant="text"
        />
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  components: {
    DynamicCard,
    List,
  },
};
</script>
