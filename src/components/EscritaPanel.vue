<script>
import json from "../assets/data.json";
import LangSwitcher from "./LangSwitcher.vue";

export default {
  data() {
    return {
      pergunta: "",
      resposta: "",
      chave: {},
      dict: json,
    };
  },
  methods: {
    greet(event) {
      alert(`Hello ${this.name}!`);
      if (event) {
        alert(event.target.tagName);
      }
    },
    capitalize: (str) =>
      str.charAt(0).toUpperCase() + str.toLowerCase().slice(1),
    busca() {
      this.resposta = "";
      this.chave = this.dict.filter(
        (x) => x[LangSwitcher.data().from] == this.pergunta.toUpperCase()
      );
      if (this.chave.length > 0) {
        for (const termo of this.chave) {
          this.resposta =
            this.resposta +
            this.capitalize(termo[LangSwitcher.data().to]) +
            ",";
        }
        let lim = this.resposta.length - 1;
        this.resposta = this.resposta.substring(0, lim) + ".";
      }
    },
  },
  components: { LangSwitcher },
};
</script>

<template>
  <p><LangSwitcher /></p>
  <input type="text" size="20" @keyup="busca" v-model="pergunta" />
  <span id="retorno">Quer dizer...{{ resposta }}</span>
</template>

<style>
input[type="text"] {
  background-color: transparent;
  font-size: 14px;
  border: 2px solid #ccc;
  border-top: none;
  border-left: none;
  border-right: none;
  color: #ccc;
}
#retorno {
  color: #ccc;
  font-size: 14px;
}
</style>
