<template>
  <div id="app">
    <HeaderComponent />
  </div>
</template>

<script>
import HeaderComponent from "@/components/HeaderComponent.vue";

export default {
  name: "App",
  // data(){
  //   return {
  //     indirizzoApi: "https://flynn.boolean.careers/exercises/api/array/music",
  //   }
  // }
  components: {
    HeaderComponent,
  },
};
</script>

<style lang="scss">
@import "./assets/style/generics.scss";
</style>
