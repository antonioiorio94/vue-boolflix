<template>
  <div class="container-fluid">
    <div class="row">
      <h2>Serie TV</h2>
      <div
        class="col-sm-12 col-md-4 col-xl-2 mb-3"
        v-for="(serie, index) in seriesList"
        :key="index"
      >
        <div class="card">
          <img
            class="mb-3"
            :src="imgUrl + serie.poster_path"
            :alt="serie.name"
          />
          <h5>{{ serie.name }}</h5>
          <p>Titolo originale: {{ serie.original_name }}</p>
          <p class="text-uppercase">Lingua: {{ serie.original_language }}</p>
          <p>Voto: {{ serie.vote_average }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SeriesList",
  props: {
    seriesList: Array,
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
