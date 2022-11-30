<template>
  <div class="container-fluid">
    <div class="flix-container">
      <ul class="flix-items">
        <li v-for="content in arrContent" :key="content">
          <a href="#">
            <div class="content">
              <h2>{{ content.title }}</h2>
            </div>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "MainPage",
  props: {
    msg: String,
  },
  data() {
    return {
      arrContent: null,
      urlApi:
        "https://api.themoviedb.org/3/movie/550?api_key=cc0c92c3f4182736e2226b57b46f8728",
    };
  },
  created() {
    axios.get(this.urlApi).then((axiosResponse) => {
      console.log(axiosResponse);
      this.arrContent = axiosResponse;
    });
  },
};
</script>

<style scoped lang="scss">
$netflixred: #e50914;
$netflixblack: #222222;
$netflixfaq: #303030;
.container-fluid {
  background-color: black;
  border-top: 10px solid $netflixfaq;
  border-bottom: 10px solid $netflixfaq;
  display: flex;
  align-items: center;
  height: 80vh;
}
.flix-container {
  position: relative;
  background-color: $netflixfaq;
  height: 270px;
  width: 100%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}

.flix-items {
  height: 20%;
  width: 100%;

  li {
    position: relative;
    vertical-align: middle;
    display: inline-block;
    list-style: none;
    width: 200px;
    height: 120px;
    background-image: url("content.");
    transition-duration: 0.5s;
    overflow: hidden;
    cursor: pointer;

    .bg-img {
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center top;
    }

    &:hover {
      transition-delay: 0.5s;
      width: 400px;
      height: 250px;
    }
  }
}
</style>
