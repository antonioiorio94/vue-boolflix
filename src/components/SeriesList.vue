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
          <div class="card-body">
            <h5>{{ serie.name }}</h5>
            <p>Titolo originale: {{ serie.original_name }}</p>
            <p class="text-uppercase">Lingua: {{ serie.original_language }}</p>
            <p>Voto: {{ serie.vote_average }}</p>
          </div>
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
@import "@/style/card-style";
</style>
