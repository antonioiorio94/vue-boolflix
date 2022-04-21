<template>
  <main>
    <MoviesList :moviesList="searchedMovies" :imgUrl="imgUrl" />
    <SeriesList :seriesList="searchedSeries" :imgUrl="imgUrl" />
  </main>
</template>

<script>
import MoviesList from "./MoviesList.vue";
import SeriesList from "./SeriesList.vue";

export default {
  name: "BoolflixMain",
  props: {
    searchedMovies: Array,
    searchedSeries: Array,
  },
  components: {
    MoviesList,
    SeriesList,
  },
  data() {
    return {
      imgUrl: "https://image.tmdb.org/t/p/w342",
    };
  },
};
</script>

<style lang="scss" scoped></style>
