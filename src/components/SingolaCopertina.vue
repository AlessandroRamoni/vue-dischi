<template>
  <div>
    <img :src="immagine" />
    <h3>{{ titolo }}</h3>
    <p>{{ anno }}</p>
  </div>
</template>

<script>
export default {
  name: "SingolaCopertina",
  props: {
    immagine: String,
    titolo: String,
    anno: String,
  },
};
</script>

<style scoped lang="scss">
</style>