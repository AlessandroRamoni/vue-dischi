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
  </div>
</template>

<script>
import SingolaCopertina from "@/components/SingolaCopertina.vue";

export default {
  name: "MainComponent",
  props: {
    insiemeDelleImmagini: Array,
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
  padding-top: 50px;
}
</style>