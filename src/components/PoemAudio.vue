<template>
  <v-btn @click="playAudio" prepend-icon="mdi-music" class="mb-4 listen"
    >Listen</v-btn
  >
  <audio ref="audio" src="poem.mp3" preload="auto"></audio>
</template>

<script>
export default {
  methods: {
    playAudio() {
      this.$refs.audio.play();
    },
  },
};
</script>
<style scoped>
.listen {
  text-transform: none;
}
</style>
