<template>
  <div class="is-flex is-align-item-center is-justify-content-space-between">
    <StopWatch :time="time" />

    <button class="button" @click="initCount" :disabled="isTimerActive">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="stopCount" :disabled="!isTimerActive">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import StopWatch from "@/components/StopWatch.vue";

export default defineComponent({
  name: "TimerManager",
  props: {},
  components: {
    StopWatch,
  },
  data() {
    return {
      time: 0,
      timer: 0,
      isTimerActive: false,
    };
  },
  methods: {
    initCount() {
      this.isTimerActive = true;
      this.timer = setInterval(() => {
        this.time += 1;
      }, 1000);
    },
    stopCount() {
      this.isTimerActive = false;
      clearInterval(this.timer);
    },
  },
});
</script>
