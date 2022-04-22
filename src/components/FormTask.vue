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
        <div
          class="is-flex is-align-item-center is-justify-content-space-between"
        >
          <section class="is-flex is-align-item-center is-align-items-center">
            <strong>{{ updateTime }}</strong>
          </section>
          <button class="button" @click="initCount">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="stopCount">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "FormTask",
  data() {
    return {
      time: 0,
      timer: 0,
    };
  },
  computed: {
    updateTime(): string {
      return new Date(this.time * 1000).toISOString().substr(11, 8);
    },
  },
  methods: {
    initCount() {
      this.timer = setInterval(() => {
        this.time += 1;
      }, 1000);
    },
    stopCount() {
      clearInterval(this.timer);
    },
  },
});
</script>
