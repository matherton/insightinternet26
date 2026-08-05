<template>
  <v-btn
    :disabled="isAudioPlaying"
    @click="playAudio"
    prepend-icon="mdi-music"
    class="mb-4 listen"
    >Listen</v-btn
  >
  <audio ref="audio" src="poem.mp3" preload="auto" @ended="audioEnded"></audio>
</template>

<script>
export default {
  data() {
    return {
      isAudioPlaying: false,
      currentIndex: 0,
    };
  },
  methods: {
    playAudio() {
      if (this.isAudioPlaying) {
        this.$refs.audio.pause();
        this.currentIndex = 0;
      } else {
        this.isAudioPlaying = true;
        this.$refs.audio.play();
        this.$emit("play");
      }
    },
    pauseAudio() {
      this.$refs.audio.pause();
      this.isAudioPlaying = false;
    },
    audioEnded() {
      this.isAudioPlaying = false;
    },
  },
};
</script>
<style scoped>
.listen {
  text-transform: none;
}
</style>
