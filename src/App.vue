<template>
  <div id="App">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Movie Revue App</h1>
    <h3>The best place to get Movie Reviews</h3>
    <Movie v-on:formSubmit="getMovieList"/>
    <br>
    <List v-text="listMovie"/>
  </div>
</template>

<script>
import Movie from "./components/Movie.vue";
import List from "./components/List.vue";
import axios from 'axios'

export default {
  name: "App",
  components: {
    Movie,
    List
  },
  data: function() {
    return {
      movieTitle: '',
      listMovie: [],
    };
  },
  methods: {
    getMovieList: function(movieTitle) {
      this.axios.get(
        "https://api.themoviedb.org/3/search/movie?api_key=7b83dfba4032b1b1d48a4e350ad6b79d&query=" +
          movieTitle
      ).then(response => {
        var ListLength = response.data.results.length
        for(var i=0; i<ListLength; i++){
          this.listMovie = response.data.results[i].title
        }
      }
      );
    }
  }
};
</script>

<style>
#App {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
