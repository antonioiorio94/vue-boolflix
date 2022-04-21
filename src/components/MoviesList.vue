<template>
  <div class="container-fluid">
    <div class="row">
      <h2>Film</h2>
      <div
        class="col-sm-12 col-md-4 col-xl-2 mb-3"
        v-for="(movie, index) in moviesList"
        :key="index"
      >
        <div class="card">
          <img
            class="mb-3"
            :src="imgUrl + movie.poster_path"
            :alt="movie.title"
          />
          <h5>{{ movie.title }}</h5>
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
    imgUrl: String,
  },
};
</script>

<style lang="scss" scoped>
.row {
  text-align: -webkit-center;
  padding: 20px;
  h2 {
    text-align: start;
    font-weight: bold;
    color: white;
    margin-bottom: 1rem;
    font-size: 1.5rem;
  }
  .card {
    padding: 20px;
    background-color: transparent;
    text-align: -webkit-center;
    margin-bottom: 2rem;
    border: 1px solid white;
    height: 100%;
    h5 {
      font-weight: bold;
    }
  }
}
</style>
