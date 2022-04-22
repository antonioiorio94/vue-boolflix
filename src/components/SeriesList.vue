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
          <div v-if="serie.poster_path === null">
            <div class="error_img">
              <h2>Copertina non disponibile</h2>
            </div>
          </div>

          <div v-else>
            <img
              class="mb-3"
              :src="imgUrl + serie.poster_path"
              :alt="serie.name"
            />
          </div>
          <div class="card-body">
            <h5>{{ serie.name }}</h5>
            <p>Titolo originale: {{ serie.original_name }}</p>
            <p class="text-uppercase">Lingua: {{ serie.original_language }}</p>
            <div>
              <p>Voto: {{ averageVote(serie.vote_average) }}</p>
              <i v-for="i in vote" :key="i" class="fa fa-2x fa-star"></i>
            </div>

            <p><span class="fw-bold">Riassunto: </span>{{ serie.overview }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SeriesList",
  data() {
    return {
      vote: [],
    };
  },
  props: {
    seriesList: Array,
    imgUrl: String,
  },
  methods: {
    //TRASFORMO IL VOTO DECIMALE IN UN VOTO DA 0 A 5
    averageVote(n) {
      this.vote = Math.ceil(n / 2);
      console.log(this.vote);
      return this.vote;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/card-style";
@import "@/style/general";

.error_img {
  background-color: $base-color;
  height: 475%;
  width: 107%;
  h2 {
    text-align: center;
    line-height: 40px;
  }
}
</style>
