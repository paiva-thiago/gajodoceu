<script>
import json from "../assets/data.json";

export default {
  data() {
    return {
      from: "",
      to: "",
      pergunta: "",
      resposta: "",
      chave: {},
      dict: json,  
      label: {
        "pt": "Português de Portugal / Português do Brasil",
        "br": "Português do Brasil / Português de Portugal",
      }
    };
  },
  methods: {
    greet(event) {
      if (event) {
        alert(event.target.tagName);
      }
    },
    capitalize: (str) =>
      str.charAt(0).toUpperCase() + str.toLowerCase().slice(1),
    busca(from,to) {
      this.resposta = "";
      this.chave = this.dict.filter(
        (x) => x[from] == this.pergunta.toUpperCase()
      );
      if (this.chave.length > 0) {
        for (const termo of this.chave) {
          this.resposta =
            this.resposta +
            this.capitalize(termo[to]) +
            ",";
        }
        let lim = this.resposta.length - 1;
        this.resposta = this.resposta.substring(0, lim) + ".";
      }
    },
  }
  };
</script>

<template>
  <h1>{{ label[from] }}</h1>
  <input type="text" size="20" @keyup="busca(from,to)" v-model="pergunta" />
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
