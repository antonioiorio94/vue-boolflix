<template>
  <main>
    <MoviesList :moviesList="searchedMovies" />
  </main>
</template>

<script>
import MoviesList from "./MoviesList.vue";

export default {
  name: "BoolflixMain",
  props: {
    searchedMovies: Array,
  },
  components: {
    MoviesList,
  },
};
</script>

<style lang="scss" scoped></style>
