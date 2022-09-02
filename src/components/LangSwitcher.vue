<script>
export default {
  data() {
    return {
      from: "pt",
      to: "br",
      icoFrom:"🇵🇹",
      icoTo:"🇧🇷"
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
  background-color:#020;
  color:#ccc;
}
</style>
