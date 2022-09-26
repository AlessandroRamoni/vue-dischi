<template>
  <div class="container">
    <SingolaCopertina
      v-for="(copertina, index) in insiemeDelleImmagini"
      :key="index"
      :immagine="copertina.poster"
      :titolo="copertina.title"
      :anno="copertina.year"
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
</style>