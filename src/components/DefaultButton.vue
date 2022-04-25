<template>
  <button class="button" @click="onClickBtn" :disabled="isDisabled">
    <span class="icon">
      <i :class="iconClass"></i>
    </span>
    <span>{{ text }}</span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "DefaultButton",
  emits: ["onClickBtn"],
  props: {
    iconClass: {
      type: String,
      default: "",
    },
    isDisabled: {
      type: Boolean,
      default: false,
    },
    text: {
      type: String,
      default: "",
    },
  },
});
</script>
