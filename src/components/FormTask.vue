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
          v-model="taskDescription"
        />
      </div>

      <div class="column">
        <Timer @endTimer="endTask" />
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
  data() {
    return { taskDescription: "" };
  },
  methods: {
    endTask(taskTime: number): void {
      console.log(`Tempo da tarefa ${taskTime}`);
      console.log(`Descricao da tarefa ${this.taskDescription}`);
      this.taskDescription = "";
    },
  },
});
</script>
