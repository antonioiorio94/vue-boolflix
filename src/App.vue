<template>
  <div id="app">
    <BoolflixHeader />
  </div>
</template>

<script>
import BoolflixHeader from "./components/BoolflixHeader.vue";

export default {
  name: "App",
  components: {
    BoolflixHeader,
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
