<script>
export default {
  data() {
    return {
      elementSearch: "",
    };
  },

  emits: ["form-input", "form-input-series"],
};
</script>

<template>
  <header>
    <div class="container d-flex justify-content-between">
      <h1>Boolflix</h1>
      <form
        class="w-25"
        @submit.prevent="$emit('form-input', elementSearch)"
        @submit="$emit('form-input-series', elementSearch)"
      >
        <div class="input-group">
          <input
            v-model="elementSearch"
            type="text"
            class="form-control"
            placeholder="Cerca il titolo del film..."
          />
          <button class="btn btn-danger" type="submit" id="button-addon2">
            Cerca
          </button>
        </div>
      </form>
    </div>
  </header>
</template>

<style>
header {
  background-color: black;
  color: #e50914;
  padding: 30px;
}
</style>
