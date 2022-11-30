<template>
  <div class="container-fluid">
    <HeaderPage></HeaderPage>
    <MainPage />
  </div>
</template>

<script>
import MainPage from "./components/MainPage.vue";
import HeaderPage from "@/components/HeaderPage.vue";

export default {
  name: "App",
  components: {
    MainPage,
    HeaderPage,
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import url("https://fonts.googleapis.com/css2?family=Lato&display=swap");
$netflixred: #e50914;
$netflixblack: #222222;
$netflixfaq: #303030;
body {
  height: 100vh;
  width: 100vw;
  font-family: "Lato", sans-serif;
}
</style>
