<template>
  <div id="app">
    <BoolflixHeader @searchedTitle="searchTitle" />
    <BoolflixMain
      :searchedMovies="selectedMovie"
      :searchedSeries="selectedSeries"
    />
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
      selectedSeries: [],
    };
  },
  methods: {
    //Richiesta Movie
    apiQueryMovie: function (searchedText) {
      this.textSearched = searchedText;

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
    //Richiesta serie TV
    apiQuerySeries: function (searchedText) {
      this.textSearched = searchedText;

      const params = {
        query: this.textSearched,
        api_key: this.apiKey,
        language: "it-IT",
      };

      axios
        .get(this.apiUrl + "tv", { params })
        .then((response) => {
          console.log(response);
          this.selectedSeries = response.data.results;
          console.log(this.selectedSeries);
          return this.selectedSeries;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    searchTitle(searchText) {
      if (searchText.length > 0) {
        this.apiQueryMovie(searchText);
        this.apiQuerySeries(searchText);
      }
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
