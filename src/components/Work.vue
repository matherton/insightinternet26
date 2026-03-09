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
          <ImageCard
            title="The Mash Tun Pub App"
            :image="MashLogo"
            tech="Vue, daisyUI, Node.js, ES6, GIMP"
            description="Developed and host a Vue application for The Mash Tun Pub. The Manager supplies monthly updates of their promotions and events, which we update the events carousel with."
            href="https://edinburghmashtun.co.uk/"
            class="logo"
          />
        </v-col>
        <v-col cols="12" md="4">
          <ImageCard
            title="The Mash Tun Menu App"
            :image="MashLogo"
            tech="React, Node.js, ES6, GIMP"
            description="Developed and host a performance-optimised React Menu Application for The Mash Tun pub. As part of our comprehensive service, we coordinated the professional food photography session."
            href="https://matherton.github.io/mash-tun/"
            class="logo"
          />
        </v-col>
        <v-col cols="12" md="4">
          <ImageCard
            title="Harkness Pies"
            :image="HarknessPie"
            tech="React, Tailwind, Node.js, ES6, UX Design"
            description="InsightInternet created a React Web Application for Harkness Pies. The system features a user-friendly interface for customers to view products and find out more about its ethos and the owner, Patrick Harkness. "
            href="https://matherton.github.io/harkness-pies/"
            class="logo"
          />
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
          <ImageCard
            :image="LlyodBank"
            jobTitle="Sapient React Consultant"
            description="Insight Internet provided React consulting services to Lloyds Banking Group via Sapient, developing a reusable component library for an internal staff support application. The app enabled banking staff to deliver real-time loan eligibility information to customers over the phone, replacing a manual process that previously took up to two weeks. Key deliverables included fully tested reusable components with Cypress coverage and seamless integration with live APIs in close collaboration with backend developers."
            class="logo"
            href="https://www.lloydsbank.com/"
          />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard
            :image="ArnoldClark"
            jobTitle="React Native Developer"
            class="logo"
            description="Insight Internet completed a remote contract with Arnold Clark to develop a native car reservation mobile app using React and Redux Saga for seamless data flow across web and mobile platforms. Working within a small mobile team, designs were delivered via Invision and implemented using ES6 and styled-components. The project also involved hands-on device testing using VS Code and Xcode to ensure optimal real-world performance."
            href="https://www.arnoldclark.com/"
          />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard
            :image="LlyodBank"
            jobTitle="BJSS React Consultant"
            class="logo"
            description="Insight Internet provided React consulting services to Lloyds Banking Group via BJSS, developing reusable components in Storybook for their React Loans Application using TypeScript in a fully agile environment. Initially based at Lloyds' Edinburgh Head Office, the team seamlessly transitioned to remote work following a Covid-19 case, maintaining project timelines throughout. Each component was approved by Product Owners before integration into the Loans App, with video demos provided to showcase reusability across different brands."
            href="https://www.lloydsbank.com/"
          />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard
            :image="ConnectAuto"
            jobTitle="React Web Developer"
            class="logo"
            description="Insight Internet collaborated with Connect Auto on a range of high-profile automotive projects, including developing a new website for Lamborghini from Invision designs and enhancing the Jaguar Land Rover site with advanced data handling via Flow and updated form submission functionality. Across the engagement, the team built reusable styled components, bespoke ES6 functionality, and SVG components for various client sites. The project also involved integrating the markdown-to-jsx package to improve content management capabilities within the CMS WYSIWYG editor."
            href="https://www.connect.auto/"
          />
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
