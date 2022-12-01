<template>
  <div class="container-fluid">
    <HeaderPage
      @movies="movieResearch"
      :movieList="movieList"
      :seriesList="seriesList"
      :show="show"
    ></HeaderPage>
    <MainPage :movieList="movieList" :seriesList="seriesList" :show="show" />
  </div>
</template>

<script>
import MainPage from "./components/MainPage.vue";
import HeaderPage from "@/components/HeaderPage.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    MainPage,
    HeaderPage,
  },
  data() {
    return {
      movieList: [],
      seriesList: [],
      show: false,
    };
  },
  methods: {
    movieResearch(select) {
      this.popular = false;
      const params = {
        query: select,
        api_key: "cc0c92c3f4182736e2226b57b46f8728",
      };
      axios
        .get(`https://api.themoviedb.org/3/search/movie`, { params })
        .then((response) => {
          this.movieList = response.data.results.slice(0, 8);
          console.log(this.movieList);
        });
      axios
        .get(`https://api.themoviedb.org/3/search/tv`, { params })
        .then((response) => {
          this.seriesList = response.data.results.slice(0, 5);
        });
    },
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
  background-color: $netflixblack;
}
</style>
