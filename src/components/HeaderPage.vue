<template>
  <nav class="navbar justify-content-between">
    <a class="navbar-brand">Booflix</a>

    <li class="nav-item"><a href="">Serie TV</a></li>
    <li class="nav-item"><a href="">FILM</a></li>
    <form action="" @submit.prevent="SearchMovie()">
      <input
        class="form-control mr-sm-2"
        type="text"
        placeholder="Search Movie"
        v-model="selectedMovie"
        @keyup.enter="SearchMovie(selectedMovie)"
      />
      <button
        @click="SearchMovie(selectedMovie)"
        type="submit"
        class="btn btn-danger"
      >
        Cerca
      </button>
    </form>
  </nav>
</template>

<script>
export default {
  name: "HeaderPage",
  data() {
    return {
      selectedMovie: "",
    };
  },
  props: {
    show: Boolean,
  },
  methods: {
    SearchMovie(selectedMovie) {
      this.$emit("movies", selectedMovie);
      this.selectedMovie = "";
    },
  },
};
</script>

<style lang="scss" scoped>
$netflixred: #e50914;
$netflixblack: #222222;
$netflixfaq: #303030;
.navbar-brand {
  font-size: 2rem;
  color: $netflixred;
}
.nav-item {
  color: white;
  list-style-type: none;
  font-size: 2rem;
}
input {
  max-width: 200px;
}
form {
  display: flex;
  gap: 1rem;
}
a {
  text-decoration: none;
  color: white;
}
.btn {
  padding: 0.5rem;
  width: 80px;
  height: 50px;
  font-size: 0.8rem;
}
</style>
