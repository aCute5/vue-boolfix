<template>
  <nav class="navbar navbar-light bg-light justify-content-between">
    <a class="navbar-brand">Booflix</a>
    <form class="form-inline">
      <input
        class="form-control mr-sm-2"
        type="search"
        placeholder="Search"
        aria-label="Search"
      />
      <button type="button" class="btn btn-danger">Cerca</button>
    </form>
  </nav>
</template>

<script>
export default {
  name: "HeaderPage",
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
input {
  max-width: 200px;
}
form {
  display: flex;
  gap: 1rem;
}
.btn {
  padding: 0.5rem;
  width: 80px;
  height: 50px;
  font-size: 0.8rem;
}
</style>
