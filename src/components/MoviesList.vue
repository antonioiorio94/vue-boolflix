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
          <div v-if="movie.poster_path === null">
            <div class="error_img">
              <h2>Copertina non disponibile</h2>
            </div>
          </div>

          <div v-else>
            <img
              class="mb-3"
              :src="imgUrl + movie.poster_path"
              :alt="movie.title"
            />
          </div>

          <div class="card-body">
            <h5>
              <span class="fw-bold">{{ movie.title }}</span>
            </h5>
            <p>
              <span class="fw-bold">Titolo originale: </span
              >{{ movie.original_title }}
            </p>
            <p class="text-uppercase">
              <span class="fw-bold">Lingua: </span>{{ movie.original_language }}
            </p>
            <p><span class="fw-bold">Voto: </span>{{ movie.vote_average }}</p>
            <p><span class="fw-bold">Riassunto: </span>{{ movie.overview }}</p>
          </div>
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
