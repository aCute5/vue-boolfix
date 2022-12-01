<template>
  <main>
    <div>
      <h1 v-if="movieList.length > 0" class="text-white">FILM</h1>
      <div class="container">
        <movie-card
          v-for="movie in movieList"
          :key="movie.id"
          :movie="movie"
          :name="movie.title"
          :originallanguage="movie.original_language"
          :originaltitle="movie.original_title"
          :langList="langList"
        />
      </div>

      <h1 v-if="seriesList.length > 0" class="text-white">SERIE TV</h1>

      <div class="container">
        <movie-card
          v-for="movie in seriesList"
          :key="movie.id"
          :movie="movie"
          :name="movie.title"
          :originalName="movie.original_title"
          :langList="langList"
        />
      </div>
    </div>
  </main>
</template>

<script>
import MovieCard from "./MovieCard.vue";

export default {
  name: "App",

  components: {
    MovieCard,
  },

  props: {
    movieList: Array,
    seriesList: Array,
    langList: Array,
    popular: Boolean,
    show: Boolean,
  },
};
</script>

<style lang="scss" scoped>
$netflixred: #e50914;
$netflixblack: #222222;
$netflixfaq: #303030;
main {
  padding: 100px 0;
  color: #bebebe;
  text-align: center;
  position: relative;
  .container {
    gap: 2rem;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
