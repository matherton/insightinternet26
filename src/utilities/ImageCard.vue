<template>
  <v-card class="mx-auto" max-width="400">
    <v-img class="align-end text-white" :src="image" cover>
      <v-card-title>{{ title }}</v-card-title>
    </v-img>

    <v-card-subtitle class="pt-4"> Number 10 </v-card-subtitle>

    <v-card-text>
      <div>Whitehaven Beach</div>

      <div>Whitsunday Island, Whitsunday Islands</div>
    </v-card-text>

    <v-card-actions>
      <v-btn color="orange" text="Share"></v-btn>

      <v-btn color="orange" text="Explore"></v-btn>
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
      required: true,
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
