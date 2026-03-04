<template>
  <v-card class="mx-auto" max-width="400" flat>
    <v-img class="align-end text-white" :src="image" cover>
      <v-card-title>{{ title }}</v-card-title>
    </v-img>

    <v-card-subtitle class="pt-4">{{ tech }}</v-card-subtitle>

    <v-card-text>
      <div>{{ description }}</div>
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="orange"
        text="Explore"
        :href="href"
        target="_blank"
        title="opens client App in new tab"
      ></v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "ImageCard",
  props: {
    title: {
      type: String,
      required: false,
    },
    image: {
      type: String,
      required: false,
    },
    tech: {
      type: String,
      required: false,
    },
    description: {
      type: String,
      required: false,
    },
    href: {
      type: String,
      required: false,
    },
  },
};
</script>

<style scoped>
.v-card-title {
  background-color: rgba(0, 0, 0, 0.5);
}
.contract .v-card-title {
  background-color: transparent;
}
</style>
