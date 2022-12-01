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
  left: 50%;
  right: 50%;
  display: flex;
  justify-content: center;
  align-content: center;
}

.card-img {
  width: 100%;
  height: 100%;
}

.vote {
  color: white;
}
</style>
