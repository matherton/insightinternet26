<template>
  <v-card :title="title" :text="text" :variant="variant"></v-card>
</template>

<script>
export default {
  name: "DynamicCard",
  props: {
    title: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: false,
    },
    text: {
      type: String,
      required: true,
    },
    variant: {
      type: String,
      default: "text",
      validator: (value) =>
        ["elevated", "flat", "tonal", "outlined", "text", "plain"].includes(
          value,
        ),
    },
  },
};
</script>
