<template>
  <div id="App">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Movie Revue App</h1>
    <h3>The best place to get Movie Reviews</h3>
    <Movie v-on:formSubmit="getMovieList"/>
    <br>
    <List v-text="movie"/>
  </div>
</template>

<script>
import Movie from "./components/Movie.vue";
import List from "./components/List.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Movie,
    List
  },
  data: function() {
    return {
      inputTitle: "",
      movie: ""
    };
  },
  methods: {
    getMovieList: function(inputTitle) {
      this.axios
        .get(
          "https://api.themoviedb.org/3/search/movie?api_key=7b83dfba4032b1b1d48a4e350ad6b79d&query=" +
            inputTitle
        )
        .then((response) => {
          var ListLength = response.data.results.length;
          // for (var i = 0; i < ListLength; i++) {
          //   this.movieTitle = response.data.results[i].title +
          //     response.data.results[i].vote_average;
          // }
          this.movie = response.data.results[0].title +": "+ response.data.results[0].vote_average + " " + response.data.results[0].overview
        });
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
