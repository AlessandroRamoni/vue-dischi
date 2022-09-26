<template>
  <div id="container-copertina">
    <div id="copertina">
      <img :src="immagine" />
      <h3>{{ titolo }}</h3>
      <p>{{ autore }}</p>
      <p>{{ anno }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingolaCopertina",
  props: {
    immagine: String,
    titolo: String,
    anno: String,
    autore: String,
  },
};
</script>

<style scoped lang="scss">
#container-copertina {
  background-color: #2e3a46;
  width: calc(100% / 5 - 30px);
  display: flex;
  flex-direction: column;
  align-items: center;
}
#copertina {
  width: 120px;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 20px;
  text-align: center;
  h3 {
    color: #ffffff;
  }
  p {
    color: #7f7f80;
    font-size: 0.8em;
  }
}
</style>