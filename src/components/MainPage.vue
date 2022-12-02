<template>
  <main>
    <div>
      <h1 v-if="movieList.length > 0" class="text-white">FILM</h1>
      <div v-else>
        <h1 class="text-white empty">
          Trova la serieTV e i film che fanno per te
        </h1>
      </div>
      <div class="container-fluid">
        <movie-card
          v-for="movie in movieList"
          :key="movie.id"
          :movie="movie"
          :name="movie.title"
          :originallanguage="movie.original_language"
          :originaltitle="movie.original_title"
          :langList="langList"
          :vote="movie.vote_average"
          :overview="movie.overview"
        />
      </div>

      <h1 v-if="seriesList.length > 0" class="text-white">SERIE TV</h1>

      <div class="container-fluid">
        <movie-card
          v-for="movie in seriesList"
          :key="movie.id"
          :movie="movie"
          :name="movie.title"
          :originalName="movie.original_title"
          :langList="langList"
          :vote="movie.vote_average"
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
    vote: Number,
    movieList: Array,
    seriesList: Array,
    langList: Array,
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
  .container-fluid {
    gap: 2rem;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
  .empty {
    font-size: 4rem;
  }
}
</style>
