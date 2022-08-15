<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criaçao de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="descricao"
        />
      </div>
      <div class="column">
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>

<script  lang="ts">
import { defineComponent } from "vue";
import Temporizador from "./Temporizador.vue";

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Formulario",
  components: { Temporizador },
  data (){
    return {
      descricao: ''
    }
  },
  methods:{
    finalizarTarefa(tempoDecorrido: number): void {
      console.log('Tempo de execursão:', tempoDecorrido);
      console.log('Descrição:', this.descricao);
      this.descricao = ''
    }
  }
});
</script>
