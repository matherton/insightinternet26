<template>
  <div class="thought-bubble">
    <div class="bubble-content">
      <transition name="fade" mode="out-in">
        <div :key="currentThought">
          <p>{{ currentThought }}</p>
        </div>
      </transition>
    </div>
    <div class="bubble-tail">
      <div class="circle circle-1"></div>
      <div class="circle circle-2"></div>
      <div class="circle circle-3"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ThoughtBubble",
  props: {
    thoughts: {
      type: Array,
      required: true,
    },
    interval: {
      type: Number,
      default: 3000,
    },
  },
  data() {
    return {
      currentIndex: 0,
      intervalId: null,
    };
  },
  computed: {
    currentThought() {
      return this.thoughts[this.currentIndex];
    },
  },
  mounted() {
    this.startCycling();
  },
  beforeUnmount() {
    this.stopCycling();
  },
  methods: {
    startCycling() {
      this.intervalId = setInterval(() => {
        this.currentIndex = (this.currentIndex + 1) % this.thoughts.length;
      }, this.interval);
    },
    stopCycling() {
      if (this.intervalId) {
        clearInterval(this.intervalId);
      }
    },
  },
};
</script>

<style scoped>
.thought-bubble {
  position: absolute;
  left: 50%;
  top: 8rem;
  display: inline-block;
  margin-bottom: 60px; /* Space for the tail circles */
}

.bubble-content {
  background: white;
  border: 3px solid #333;
  border-radius: 50%;
  padding: 30px 40px;
  position: relative;
  min-width: 200px;
  min-height: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-family: "Comic Sans MS", cursive, sans-serif;
  font-size: 16px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.bubble-tail {
  position: absolute;
  bottom: -50px;
  left: 30px;
}

.circle {
  background: white;
  border: 3px solid #333;
  border-radius: 50%;
  position: absolute;
}

.circle-1 {
  width: 30px;
  height: 30px;
  bottom: 20px;
  left: 0;
}

.circle-2 {
  width: 20px;
  height: 20px;
  bottom: 1px;
  left: -10px;
}

.circle-3 {
  width: 12px;
  height: 12px;
  bottom: -10px;
  left: -17px;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
