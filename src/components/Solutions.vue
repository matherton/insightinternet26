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
  <div id="solutions-section" style="scroll-margin-top: 6rem">
    <v-container>
      <div class="solution">
        <h1 class="subheading grey--text"></h1>
        <v-row>
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-img
              src="../assets/pie.png"
              alt="Solutions Image"
              class="solution-image"
            />
          </v-col>
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-img
              src="../assets/pie.png"
              alt="Solutions Image"
              class="solution-image"
            />
          </v-col>
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-img
              src="../assets/pie.png"
              alt="Solutions Image"
              class="solution-image"
            />
          </v-col>
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-img
              src="../assets/pie.png"
              alt="Solutions Image"
              class="solution-image"
            />
          </v-col>
        </v-row>
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
  </div>
</template>
<script>
export default {
  data() {
    return {
      solutions: [
        {
          title: "Why Choose Us?",
          subtitle: "Collaboration and Innovation:",
          text: "We work closely with our clients to understand their goals and deliver solutions that exceed expectations. At InsightInternet, we stay at the forefront of technology trends to bring the most advanced solutions to your business.",
        },
        {
          title: "Services:",
          subtitle: "Custom Software Development",
          text: "We offer a range of services to help you achieve your goals. From custom applications to web development, tailored to meet your specific needs. Contact us today to learn more about our services.",
        },
        {
          title: "Support:",
          subtitle: "Maintenance and Support",
          text: "Comprehensive maintenance and support services to ensure your applications run smoothly. Hosting packages available to suit your needs with ongoing updates and troubleshooting to keep your applications running smoothly.",
        },
        {
          title: "Trusted Partner:",
          subtitle: "Consultation and Reliability:",
          text: "Expert advice and consultation to help you make informed decisions about your technology stack. Depend on InsightInternet for consistent, high-quality service and ongoing support.",
        },
      ],
    };
  },
};
</script>
