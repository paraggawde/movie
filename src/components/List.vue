<template>
    <div id="List">
        <ul>
            <li v-for="movie in movies" :v-bind='movie.title'>
                <span>{{movie}}</span>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: "List",
//   props: ["movie"],

  data() {
    return {
        movie:'',
        movies:[]
    };
  }
};
</script>

