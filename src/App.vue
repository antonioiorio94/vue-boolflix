<template>
  <div id="app">
    <BoolflixHeader @searchedTitle="apiQuery" />
    <BoolflixMain :searchedMovies="selectedMovie" />
  </div>
</template>

<script>
import BoolflixHeader from "./components/BoolflixHeader.vue";
import BoolflixMain from "./components/BoolflixMain.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    BoolflixHeader,
    BoolflixMain,
  },
  data() {
    return {
      textSearched: "",
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "728f321f4e1478d4908741def6f96176",
      selectedMovie: [],
    };
  },
  methods: {
    apiQuery: function (searchedText) {
      this.textSearched = searchedText;
      console.log("apiQuery è questo:", this.textSearched);
      const params = {
        query: this.textSearched,
        api_key: this.apiKey,
        language: "it-IT",
      };

      axios
        .get(this.apiUrl + "movie", { params })
        .then((response) => {
          console.log(response);
          this.selectedMovie = response.data.results;
          console.log(this.selectedMovie);
          return this.selectedMovie;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss">
@import "@/style/general";

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
