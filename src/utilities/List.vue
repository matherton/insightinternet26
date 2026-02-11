<script setup>
const items = [
  { text: "Innovation", icon: "mdi-lightbulb" },
  { text: "Quality", icon: "mdi-star" },
  { text: "Collaboration", icon: "mdi-account-group" },
  { text: "Integrity", icon: "mdi-shield-check" },
];
</script>
<template>
  <v-card class="mx-auto" max-width="300" style="margin: 0">
    <v-list density="compact">
      <v-list-subheader><h2>Values</h2></v-list-subheader>

      <v-list-item
        v-for="(item, i) in items"
        :key="i"
        :value="item"
        color="primary"
      >
        <template v-slot:prepend>
          <v-icon :icon="item.icon"></v-icon>
        </template>

        <v-list-item-title v-text="item.text"></v-list-item-title>
      </v-list-item>
    </v-list>
  </v-card>
</template>
