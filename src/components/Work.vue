<script setup>
import ImageCard from "@/utilities/ImageCard.vue";
import MashLogo from "@/assets/mash-logo.jpg";
import HarknessPie from "@/assets/pie.png";
import LlyodBank from "@/assets/lloyds-bank-logo.png";
import ArnoldClark from "@/assets/arnold-clark-logo.png";
import ConnectAuto from "@/assets/connect-auto-logo.png";
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
  <div id="work-section" style="scroll-margin-top: 6rem">
    <v-container>
      <v-row>
        <v-col cols="12" md="4">
          <ImageCard title="The Mash Tun" :image="MashLogo" class="logo" />
        </v-col>
        <v-col cols="12" md="4">
          <ImageCard title="The Mash Tun" :image="MashLogo" class="logo" />
        </v-col>
        <v-col cols="12" md="4">
          <ImageCard title="Harkness Pies" :image="HarknessPie" class="logo" />
        </v-col>
      </v-row>
    </v-container>
    <v-divider
      color="primary"
      opacity=".7"
      thickness="3"
      variant="single"
      gradient
    >
      Contract Work
    </v-divider>
    <v-container class="contract">
      <v-row>
        <v-col cols="12" md="3">
          <ImageCard :image="LlyodBank" class="logo" />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard :image="ArnoldClark" class="logo" />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard :image="LlyodBank" class="logo" />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard :image="ConnectAuto" class="logo" />
        </v-col>
      </v-row>
    </v-container>
  </div>
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
      HarknessPie,
      LlyodBank,
      ArnoldClark,
      ConnectAuto,
    };
  },
};
</script>
