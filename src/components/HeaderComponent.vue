<template>
  <header>
    <img src="../assets/img/logospotify.webp" alt="" />
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
};
</script>

<style scoped lang="scss">
header {
  background-color: #2e3a46;
}
img {
  width: 35px;
  display: block;
  border-radius: 50%;
  margin-left: 20px;
  padding-top: 20px;
  padding-bottom: 20px;
}
</style>