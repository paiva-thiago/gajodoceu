<script>
export default {
  data() {
    localStorage.setItem("from", "pt");
    localStorage.setItem("to", "br");
    return {
      from: "pt",
      to: "br",
      icoFrom: "🇵🇹",
      icoTo: "🇧🇷",
    };
  },
  methods: {
    troca() {
      let aux = this.from;
      this.from = this.to;
      this.to = aux;
      aux = this.icoFrom;
      this.icoFrom = this.icoTo;
      this.icoTo = aux;
      localStorage.setItem("from", this.from);
      localStorage.setItem("to", this.to);
    },
  },
};
</script>
<template>
  <button id="sw" @click="troca">
    Quero traduzir de {{ icoFrom }} para {{ icoTo }}
  </button>
</template>

<style>
#sw {
  font-size: 28px;
  background-color: transparent;
  border-radius: 10px;
  border-color: #ccc;
  background-color: #020;
  color: #ccc;
}
</style>
