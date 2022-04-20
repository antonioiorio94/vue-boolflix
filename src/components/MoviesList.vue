<template>
  <div class="container">
    <div class="row">
      <div class="col-3" v-for="(movie, index) in moviesList" :key="index">
        <div class="card">
          <h4>{{ movie.title }}</h4>
          <p>Titolo originale: {{ movie.original_title }}</p>
          <p class="text-uppercase">Lingua: {{ movie.original_language }}</p>
          <p>Voto: {{ movie.vote_average }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MoviesList",
  props: {
    moviesList: Array,
  },
};
</script>

<style lang="scss" scoped>
.card {
  padding: 20px;
  width: 200px;
}
</style>
