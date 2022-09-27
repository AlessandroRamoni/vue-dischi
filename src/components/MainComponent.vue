<template>
  <div class="container">
    <SingolaCopertina
      v-for="(copertina, index) in insiemeDelleImmagini"
      :key="index"
      :immagine="copertina.poster"
      :titolo="copertina.title"
      :anno="copertina.year"
      :autore="copertina.author"
    />
    <input type="text" v-model="searchText" @keyup.enter="doSearch()" />
  </div>
</template>

<script>
import SingolaCopertina from "@/components/SingolaCopertina.vue";

export default {
  name: "MainComponent",
  data() {
    return {
      searchText: "",
    };
  },
  props: {
    insiemeDelleImmagini: Array,
  },
  methods: {
    doSearch() {
      this.$emit("search", this.searchText);
      console.log(this.searchText);
    },
  },
  components: {
    SingolaCopertina,
  },
};
</script>

<style scoped lang="scss">
.container {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  justify-content: space-around;
  padding-top: 10px;
}
input {
  background-color: rgb(238, 62, 62);
}
</style>