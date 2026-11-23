<script setup>
import List from "../utilities/List.vue";
import DynamicCard from "../utilities/DynamicCard.vue";
import pauseLogo from "@/assets/pauseai-banner-BG.png";
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
      <v-col cols="12" md="3">
        <DynamicCard
          title="Story"
          text="InsightInternet was founded with a vision to support startups by providing top-notch applications. Based in Edinburgh and partnering with Edinburgh startups and small businesses, we leverage the latest technologies to create seamless, responsive, and scalable applications."
          variant="text"
        />
      </v-col>
      <!-- inline style above to ensure this header is not scrolled behind sticky nav bar -->
      <v-col cols="12" md="3">
        <List :items="items" />
      </v-col>

      <v-col cols="12" md="3">
        <DynamicCard
          title="Mission Statement"
          text="Our mission is to empower startups with robust and scalable applications, ensuring they have the technological edge to succeed in a competitive market. We grow together through training, consulting & hosting."
          variant="text"
        />
      </v-col>
      <v-col cols="12" md="3" style="padding: 0 2rem 1rem 1.75rem">
        <v-img :width="150" aspect-ratio="16/9" :src="pauseLogo"></v-img>
        <p style="font-size: 0.875rem">
          Have been working with PauseAI since 2025, attending weekly online meetings and helping to organise and attended:
          <ul style="margin-left: 1rem">
            <li><a href="https://luma.com/mpan6y4o?tk=Q1eXfB" target="_blank">PauseAI March to Stop AI Data Centres</a></li>
            <li><a href="https://luma.com/6jp2nqe9?tk=gixpVc" target="_blank">Panel Discussion: Who's Responsible When AI Goes Wrong</a></li>
            <li><a href="https://luma.com/j627zgd2" target="_blank">the first public meeting</a> for PauseAI Scotland</li>
          </ul>
        </p>
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
