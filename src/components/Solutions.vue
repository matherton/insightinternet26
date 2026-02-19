<script setup>
import { VCard } from "vuetify/components";
</script>

<template>
  <v-divider
    color="primary"
    opacity=".7"
    thickness="10"
    variant="double"
    gradient
  >
    Solutions
  </v-divider>
  <div id="solutions-section" class="solutions" style="scroll-margin-top: 6rem">
    <h1>This is the solutions section</h1>
  </div>
  <v-container>
    <div class="solution">
      <h1 class="subheading grey--text"></h1>
      <v-row>
        <v-col
          cols="12"
          sm="6"
          md="4"
          lg="3"
          v-for="solution in solutions"
          :key="solution.title"
        >
          <v-card flat>
            <v-card-title>{{ solution.title }}</v-card-title>
            <v-card-subtitle>{{ solution.subtitle }}</v-card-subtitle>
            <v-card-text>{{ solution.text }}</v-card-text>
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
      solutions: [
        {
          title: "Custom Software Development",
          subtitle:
            "We specialize in creating custom software solutions tailored to your unique business needs.",
          text: "Whether you need a web application, mobile app, or enterprise software, our team of experienced developers will work closely with you to design and build a solution that drives efficiency, enhances user experience, and supports your business goals.",
          image: "/images/solutions.png",
        },
        {
          title: "Custom Development",
          subtitle:
            "We specialize in creating custom software solutions tailored to your unique business needs.",
          text: "Whether you need a web application, mobile app, or enterprise software, our team of experienced developers will work closely with you to design and build a solution that drives efficiency, enhances user experience, and supports your business goals.",
          image: "/images/solutions.png",
        },
        {
          title: "Software Development",
          subtitle:
            "We specialize in creating custom software solutions tailored to your unique business needs.",
          text: "Whether you need a web application, mobile app, or enterprise software, our team of experienced developers will work closely with you to design and build a solution that drives efficiency, enhances user experience, and supports your business goals.",
          image: "/images/solutions.png",
        },
        {
          title: "Lorium ipsum dolor sit amet",
          subtitle:
            "We specialize in creating custom software solutions tailored to your unique business needs.",
          text: "Whether you need a web application, mobile app, or enterprise software, our team of experienced developers will work closely with you to design and build a solution that drives efficiency, enhances user experience, and supports your business goals.",
          image: "/images/solutions.png",
        },
      ],
    };
  },
};
</script>
