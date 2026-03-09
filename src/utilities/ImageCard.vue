<template>
  <section>
    <v-card class="mx-auto" max-width="400" flat>
      <v-img class="align-end text-white" :src="image" cover mb-4>
        <v-card-title>{{ title }}</v-card-title>
      </v-img>

      <strong v-if="jobTitle">{{ jobTitle }}</strong>

      <v-card-subtitle class="pt-4">{{ tech }}</v-card-subtitle>

      <v-card-actions>
        <v-btn
          @click="toggleDescription"
          color="orange"
          target="_blank"
          title="opens client App in new tab"
        >
          {{ revealdescription ? "Hide Description" : "Show Description" }}
        </v-btn>
      </v-card-actions>
    </v-card>
  </section>
  <v-card-text style="padding-top: 0">
    <v-expand-transition>
      <p v-if="revealdescription" class="description" style="width: 100%">
        {{ description }}
      </p>
    </v-expand-transition>
    <v-btn color="orange" text="Explore" :href="href" target="_blank">
      Explore
    </v-btn>
  </v-card-text>
</template>

<script>
import { ref } from "vue";

export default {
  name: "ImageCard",
  props: {
    title: {
      type: String,
      required: false,
    },
    jobTitle: {
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
    image: {
      type: String,
      required: true,
    },
    href: {
      type: String,
      required: false,
    },
  },
  setup() {
    const revealdescription = ref(false);

    function toggleDescription() {
      revealdescription.value = !revealdescription.value;
    }

    return {
      revealdescription,
      toggleDescription,
    };
  },
};
</script>

<style scoped>
.description {
  margin: 0;
  width: 100%;
}
</style>
