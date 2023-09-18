<script>
import { store } from "../data/store";
import AppSeriesCard from "./AppSeriesCard.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: { AppSeriesCard },
};
</script>

<template>
  <div class="container my-5">
    <h3 v-show="store.Series.length > 0">Series List:</h3>

    <div
      class="row d-flex justify-content-center gap-2 g-2 row-cols-2 row-cols-md-3 row-cols-lg-4"
    >
      <AppSeriesCard
        v-for="serie in store.Series"
        :key="serie.id"
        :title="serie.name"
        :original_title="serie.original_name"
        :original_language="serie.original_language"
        :vote_average="Math.ceil(serie.vote_average / 2)"
        :poster_path="serie.poster_path"
        :overview="serie.overview"
      />
    </div>
  </div>
</template>

<style lang="scss">
h3 {
  color: #e50914;
}
</style>
