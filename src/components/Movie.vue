<template>
    <div id="Movie">
        <form v-on:submit.prevent='getMovieList(inputTitle)'>
            <input type="text" v-model="inputTitle">
            <input type="submit" value="Submit">
        </form>
        <div id="movieDisplay" v-for="movie in movies">
            <p> {{movie.title}}</p>
            <p>{{movie.vote_average}}</p>
            <p>{{movie.overview}}</p>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
  name: "Movie",
  data: function() {
    return {
      inputTitle: "",
      movies:"",
    };
  },
  methods: {
    getMovieList: function(inputTitle) {
      axios.get("https://api.themoviedb.org/3/search/movie?api_key=7b83dfba4032b1b1d48a4e350ad6b79d&query=" +
            inputTitle
        )
        .then((response) => {
            this.movies = response.data.results;
        });
    }
  }
};
</script>

