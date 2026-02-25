<script setup>
import DynamicCard from "@/utilities/DynamicCard.vue";
import ImageCard from "@/utilities/ImageCard.vue";
import MashLogo from "@/assets/mash-logo.jpg";
</script>
<template>
  <v-divider
    color="primary"
    opacity=".7"
    thickness="10"
    variant="double"
    gradient
  >
    Work
  </v-divider>
  <div id="work-section" class="work" style="scroll-margin-top: 6rem">
    <h1>This is the work section</h1>
  </div>
  <DynamicCard
    title="Card Title"
    text="This is some sample text for the card."
    variant="elevated"
    image="../assets/logo.png"
  />
  <ImageCard title="The Mash Tun" :image="MashLogo" class="logo" />
</template>
<script>
export default {
  name: "Work",
  components: {
    ImageCard,
  },
  data() {
    return {
      MashLogo,
    };
  },
};
</script>
