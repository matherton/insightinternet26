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
            description="
            Banking Staff Support Application
Client: Lloyds Banking Group

Industry: Finance

Project Duration: 6 months

Project Description: Insight Internet provided React consulting services to Lloyds Banking Group through Sapient. The project involved the development of a reusable component library for a staff support application. The application was designed to assist banking staff in providing real-time loan eligibility information to customers over the phone. This innovative solution replaced a manual process that previously took up to two weeks, significantly improving efficiency and customer satisfaction.

Tools Used: React, Cypress, REST APIs

Results:

Streamlined loan eligibility checks from two weeks to real-time.
Enhanced customer service with instant data retrieval.
Developed reusable components with comprehensive Cypress test coverage.
Seamless integration with live APIs in collaboration with backend developers."
            class="logo"
            href="https://www.lloydsbank.com/"
          />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard
            :image="ArnoldClark"
            jobTitle="React Native Developer"
            class="logo"
            description="Car Reservation Mobile App
Client: Arnold Clark

Industry: Automotive

Project Duration: 5 months

Project Description: Insight Internet undertook a remote contract with Arnold Clark to develop their car reservation mobile app. The app was developed using React and relied on Redux Saga for data management between web and mobile platforms. The project involved using VS Code and Xcode for actual device testing. Working within a small mobile team, the designs were delivered via Invision, and the app's functionality and design were implemented using ES6 and styled-components.

Tools Used: React, Redux Saga, VS Code, Xcode, ES6, styled-components, Invision

Results:

Successfully developed a native mobile app for car reservations.
Ensured seamless data flow between web and mobile using Redux Saga.
Implemented design and functionality as per Invision prototypes.
Conducted thorough testing on actual devices to ensure optimal performance.
"
            href="https://www.arnoldclark.com/"
          />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard
            :image="LlyodBank"
            jobTitle="BJSS React Consultant"
            class="logo"
            description="React Loans Application Component Development
Client: Lloyds Banking Group

Industry: Finance

Project Duration: 5 months

Project Description: Insight Internet, through BJSS, provided React consulting services to Lloyds Banking Group. The project involved the development of reusable components in Storybook for their React Loans Application. The development was conducted in a fully agile environment, leveraging VS Code and TypeScript. Initially based at Lloyds' Head Office in Edinburgh, the team transitioned to remote work following a Covid-19 case. Each component, once approved by Product Owners, was integrated into the Loans App, enhancing its modularity and reusability.

Tools Used: React, Storybook, TypeScript, VS Code, MS Teams

Results:

Successfully transitioned to remote work without impacting project timelines.
Developed reusable components in Storybook, ensuring consistency and reusability.
Enhanced collaboration and productivity using MS Teams.
Provided comprehensive video demos to showcase component reusability across different brands."
            href="https://www.lloydsbank.com/"
          />
        </v-col>
        <v-col cols="12" md="3">
          <ImageCard
            :image="ConnectAuto"
            jobTitle="React Web Developer"
            class="logo"
            description="Website Development and Enhancements
Client: Connect Auto

Industry: Automotive

Project Duration: 6 months

Project Description: Insight Internet collaborated with Connect Auto on various high-profile automotive projects, including the development of a website for Lamborghini and updates to the Jaguar Land Rover site. The Lamborghini project involved creating a website based on designs provided via Invision. The Jaguar Land Rover project included adding new functionality such as data handling with Flow and updating the main page after form submission. Additionally, Insight Internet worked on various client websites, creating reusable styled components, bespoke ES6 functionality, SVG components, and integrating the markdown-to-jsx package to enhance the CMS WYSIWYG editor.

Tools Used: React, Flow, ES6, styled-components, SVG, JSON, markdown-to-jsx, Invision

Results:

Successfully developed a website for Lamborghini with high-fidelity design implementation.
Enhanced Jaguar Land Rover site with advanced data handling and updated functionality.
Created reusable components and bespoke functionality to improve efficiency and maintainability.
Integrated markdown-to-jsx for enhanced content management capabilities."
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
