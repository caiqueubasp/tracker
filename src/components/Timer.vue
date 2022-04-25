<template>
  <div class="is-flex is-align-item-center is-justify-content-space-between">
    <StopWatch :time="time" />

    <DefaultButton
      iconClass="fas fa-play"
      text="play"
      :isDisabled="isTimerActive"
      @click="initCount"
    />

    <DefaultButton
      iconClass="fas fa-stop"
      text="stop"
      :isDisabled="!isTimerActive"
      @click="stopCount"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import StopWatch from "@/components/StopWatch.vue";
import DefaultButton from "@/components/DefaultButton.vue";

export default defineComponent({
  name: "TimerManager",
  emits: ["endTimer"],
  props: {},
  components: {
    StopWatch,
    DefaultButton,
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
      this.$emit("endTimer", this.timer);
      this.timer = 0;
    },
  },
});
</script>
