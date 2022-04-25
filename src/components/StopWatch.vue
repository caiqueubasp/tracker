<template>
  <section class="is-flex is-align-item-center is-align-items-center">
    <strong>{{ updateTime }}</strong>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "StopWatch",
  props: {
    time: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    updateTime(): string {
      return new Date(this.time * 1000).toISOString().substr(11, 8);
    },
  },
});
</script>
