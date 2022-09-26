<template>
  <div id="app">
    <HeaderComponent />
    <MainComponent :insiemeDelleImmagini="arrayAppoggio" />
  </div>
</template>

<script>
import axios from "axios";
import HeaderComponent from "@/components/HeaderComponent.vue";
import MainComponent from "@/components/MainComponent.vue";

export default {
  name: "App",
  data() {
    return {
      indirizzoApi: "https://flynn.boolean.careers/exercises/api/array/music",
      arrayAppoggio: [],
    };
  },
  created() {
    console.log("caricamento dati");
    axios
      .get(this.indirizzoApi)
      .then(({ status, data }) => {
        if (status === 200) {
          this.arrayAppoggio = data.response;
          console.log(data.response);
        }
      })
      .catch((error) => {
        console.log(error);
      });
  },

  components: {
    HeaderComponent,
    MainComponent,
  },
};
</script>

<style lang="scss">
@import "./assets/style/generics.scss";
@import url("https://fonts.googleapis.com/css2?family=Luckiest+Guy&display=swap");
#app {
  height: calc(100vh);
  background-color: #1e2d3b;
  font-family: "Luckiest Guy", cursive;
}
</style>
