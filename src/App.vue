<template>
  <v-app>
    <App-header />
    <v-main>
      <router-view />
    </v-main>
    <App-footer />
  </v-app>
</template>

<script setup>
import AppHeader from "./components/AppHeader.vue";
import AppFooter from "./components/AppFooter.vue";
</script>
