<template>
    <div id="List">
        <ul>
            <li v-for="movie in movies" :v-bind="movie.title">
                {{movie.original_title}}
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
      movies:[],
      movie:''
    };
  }
};
</script>

