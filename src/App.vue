<template>
  <div id="app">
    <BoolflixHeader />
  </div>
</template>

<script>
import BoolflixHeader from "./components/BoolflixHeader.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    BoolflixHeader,
  },
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "728f321f4e1478d4908741def6f96176",
    };
  },
  mounted() {
    const query = "ritorno";
    const params = {
      query,
      api_key: this.apiKey,
      language: "it-IT",
    };

    axios
      .get(this.apiUrl + "tv", { params })
      .then((response) => {
        console.log(response);
      })
      .catch((error) => {
        console.log(error);
      });
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
