<template>
  <div id="app">
    <HeaderComponent />
  </div>
</template>

<script>
import axios from "axios";
import HeaderComponent from "@/components/HeaderComponent.vue";

export default {
  name: "App",
  data() {
    return {
      indirizzoApi: "https://flynn.boolean.careers/exercises/api/array/",
      arrayAppoggio: [],
    };
  },
  created() {
    console.log("caricamento dati");
    axios.get(this.indirizzoApi + "music").then(({ status, data }) => {
      if (status === 200) {
        this.arrayAppoggio = data;
      }
      console.log(data);
    });
  },

  components: {
    HeaderComponent,
  },
};
</script>

<style lang="scss">
@import "./assets/style/generics.scss";
#app {
  height: calc(100vh);
  background-color: #1e2d3b;
}
</style>
