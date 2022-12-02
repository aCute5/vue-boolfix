<template>
  <div class="container-cards">
    <div class="card" style="width: 20rem">
      <img
        :src="`https://www.themoviedb.org/t/p/original${movie.poster_path}`"
        class="card-img"
        alt="..."
      />
      <div class="card-back">
        <div class="card-body">
          <h5 class="card-title text-bold">
            Title: <strong>{{ name }}</strong>
          </h5>
          <h5 class="card-title">
            Original Title: <strong>{{ originaltitle }}</strong>
          </h5>
          <h6 class="card-title">
            Lingua Originale:
            <strong> <lang-flag :iso="originallanguage" /></strong>
          </h6>

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
              <p class="card-text">
                {{ overview }}
              </p>
            </span>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LangFlag from "vue-lang-code-flags";
export default {
  name: "MovieCard",
  components: {
    LangFlag,
  },
  props: {
    movie: Object,
    name: String,
    originaltitle: String,
    originallanguage: String,
    vote: Number,
    overview: String,
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.card {
  background-color: black;
  position: relative;
}
.card-back {
  display: none;
}
.card:hover .card-img {
  opacity: 0;
}
.card:hover .card-back {
  position: absolute;
  display: flex;
  justify-content: center;
  align-content: center;
  width: 100%;
}
.card-back .card-body {
  align-items: center;
}
.card-title {
  font-size: 1.5rem;
}
.card-img {
  width: 100%;
  height: 100%;
}
.card-body {
}

.vote {
  color: yellow;
}
</style>
