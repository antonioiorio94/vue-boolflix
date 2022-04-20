<template>
  <div class="container-fluid">
    <div class="row justify-content-between">
      <div class="col-4">
        <h3>Boolflix</h3>
      </div>
      <div class="col-4 d-flex justify-content-evenly">
        <input type="text" placeholder="Cerca tra film o serie TV..." />
        <button class="btn">Cerca</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BoolflixHeader",
  props: {},
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
