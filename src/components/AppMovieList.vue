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
  <div class="container">
    <h3 v-show="store.Movies.length > 0">Movie List:</h3>
    <div
      class="row d-flex justify-content-center gap-2 g-2 row-cols-2 row-cols-md-3 row-cols-lg-4"
    >
      <AppMovieCard
        v-for="movie in store.Movies"
        :key="movie.id"
        :title="movie.title"
        :original_title="movie.original_title"
        :original_language="movie.original_language"
        :vote_average="Math.ceil(movie.vote_average / 2)"
        :poster_path="movie.poster_path"
        :overview="movie.overview"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped>
h3 {
  color: #e50914;
}
</style>
