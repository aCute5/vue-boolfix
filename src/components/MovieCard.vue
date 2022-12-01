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
        <h6 class="card-title">Lingua Originale: {{ originallanguage }}</h6>
        <p class="card-text">
          Valutazione:
          <span>
            <font-awesome-icon
              v-for="star in vote"
              :key="star"
              class="vote"
              icon="fa-solid fa-star"
              >{{ star }}</font-awesome-icon
            >
          </span>
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
    vote: Number,
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.card {
  background-color: black;
}
.vote {
  color: white;
}
</style>
