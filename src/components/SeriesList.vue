<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-2" v-for="(serie, index) in seriesList" :key="index">
        <div class="card">
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
  },
};
</script>

<style lang="scss" scoped>
.row {
  text-align: -webkit-center;
  padding: 20px;
  .card {
    padding: 20px;
    width: 200px;
    text-align: -webkit-center;
    margin-bottom: 2rem;
    h5 {
      font-weight: bold;
    }
  }
}
</style>
