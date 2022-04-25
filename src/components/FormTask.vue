<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário de Criacao de Nova Tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa voce deseja iniciar?"
        />
      </div>

      <div class="column">
        <Timer />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Timer from "@/components/Timer.vue";

export default defineComponent({
  name: "FormTask",
  components: {
    Timer,
  },
});
</script>
