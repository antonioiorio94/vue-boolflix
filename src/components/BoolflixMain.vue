<template>
  <main>
    <MoviesList :moviesList="searchedMovies" />
    <SeriesList :seriesList="searchedSeries" />
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
};
</script>

<style lang="scss" scoped></style>
