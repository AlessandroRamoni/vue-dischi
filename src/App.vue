<template>
  <div id="app">
    <HeaderComponent />
    <!-- <LoaderComponent /> -->
    <MainComponent
      :insiemeDelleImmagini="arrayAppoggio"
      @search="filterCharacters"
    />
  </div>
</template>

<script>
import axios from "axios";
import HeaderComponent from "@/components/HeaderComponent.vue";
import MainComponent from "@/components/MainComponent.vue";
// import LoaderComponent from "@/components/LoaderComponent.vue";

export default {
  name: "App",
  data() {
    return {
      indirizzoApi: "https://flynn.boolean.careers/exercises/api/array/music",
      arrayAppoggio: [],
      loading: true,
    };
  },
  created() {
    axios
      .get(this.indirizzoApi)
      .then(({ status, data }) => {
        if (status === 200) {
          this.arrayAppoggio = data.response;
          console.log(data.response);
        } else {
          console.log(status);
        }
      })
      .catch((error) => {
        console.log(error);
        // this.loading = false;
      });
  },
  methods: {
    filterCharacters(textToFilter) {
      this.textToFilter = textToFilter;
      console.log(textToFilter);
      const array = [];
      this.arrayAppoggio.forEach((item) => {
        if (item.genre.indexOf(textToFilter.trim()) > -1) {
          array.push(item);
        }
      });
      this.arrayAppoggio = array;
    },
  },
  /*
      
    */

  components: {
    HeaderComponent,
    MainComponent,
    // LoaderComponent,
  },
};
</script>

<style lang="scss">
@import "./assets/style/generics.scss";
@import url("https://fonts.googleapis.com/css2?family=Luckiest+Guy&display=swap");
$ColoreSfondo: #1e2d3b;
#app {
  height: calc(100vh);
  background-color: $ColoreSfondo;
  font-family: "Luckiest Guy", cursive;
}
</style>
