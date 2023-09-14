<script>
export default {
  data() {
    return {};
  },
};
</script>

<template>
  <header>
    <div class="container d-flex justify-content-between">
      <h1>Boolflix</h1>
      <div class="input-group mb-3 w-50">
        <input
          type="text"
          class="form-control"
          placeholder="Recipient's username"
          aria-label="Recipient's username"
          aria-describedby="button-addon2"
        />
        <button
          class="btn btn-outline-secondary"
          type="button"
          id="button-addon2"
        >
          Serch
        </button>
      </div>
    </div>
  </header>
</template>

<style>
header {
  background-color: black;
  color: red;
  padding: 30px;
}
</style>
