<script>
import { store } from "../data/store";
import AppMovieCard from "./AppMovieCard.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: { AppMovieCard },
};
</script>

<template>
  <div class="container my-5">
    <div
      class="row d-flex justify-content-center gap-2 g-2 row-cols-2 row-cols-md-3 row-cols-lg-4"
    >
      <AppMovieCard
        v-for="movie in store.Movies"
        :key="movie.id"
        :title="movie.title"
        :original_title="movie.original_title"
        :original_language="movie.original_language"
        :vote_average="movie.vote_average"
      />
    </div>
  </div>
</template>

<style></style>
