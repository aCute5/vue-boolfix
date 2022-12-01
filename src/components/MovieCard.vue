<template>
  <div class="container-cards">
    <div class="card" style="width: 18rem">
      <img
        :src="`https://www.themoviedb.org/t/p/original${movie.poster_path}`"
        class="card-img-top"
        alt="..."
      />
      <div class="card-body">
        <h5 class="card-title">{{ name }}</h5>
        <h5 class="card-title">{{ originaltitle }}</h5>
        <p class="card-text">
          Lingua Originale: {{ originallanguage }}
          <span></span>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MovieCard",

  props: {
    movie: Object,
    langList: Array,
    name: String,
    originaltitle: String,
    originallanguage: String,
  },

  methods: {
    getStars(vote) {
      return Math.round(vote / 2);
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  background-color: black;
}
</style>
