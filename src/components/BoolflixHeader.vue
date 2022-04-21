<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-sm-6 col-4">
        <h3>Boolflix</h3>
      </div>
      <div class="col-sm-6 col-4 d-flex justify-content-end">
        <input
          v-model="searchedText"
          type="text"
          placeholder="Cerca tra film o serie TV..."
        />
        <button @click="$emit('searchedTitle', searchedText)" class="btn">
          Cerca
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BoolflixHeader",
  data() {
    return {
      searchedText: "",
    };
  },
};
</script>

<style scoped lang="scss">
@import "@/style/general";

.row {
  background-color: black;
  align-items: center;
  padding: 10px;
  h3 {
    color: $base-color;
    font-weight: bolder;
  }
  input {
    width: 20rem;
    background: none;
    border: none;
    color: white;
  }
  button {
    border: 1px solid white;
    color: white;
  }
}
</style>
