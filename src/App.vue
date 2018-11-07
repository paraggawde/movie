<template class="card">
  <div id="app" class="card-body">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Movie Revue App</h1>
    <h3>The best place to get Movie Reviews</h3>
    <Movie/>
  </div>
</template>

<script>
import Movie from "./components/Movie.vue";

export default {
  name: "app",
  components: {
    Movie
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Roboto');

#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img{
  height: 100px;
}
</style>
