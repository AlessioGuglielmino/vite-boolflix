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
  <hr />

  <div class="container my-5">
    <div
      class="row d-flex justify-content-center gap-2 g-2 row-cols-2 row-cols-md-3 row-cols-lg-4"
    >
      <AppSeriesCard
        v-for="serie in store.Series"
        :key="serie.id"
        :title="serie.name"
        :original_title="serie.original_name"
        :original_language="serie.original_language"
        :vote_average="serie.vote_average"
      />
    </div>
  </div>
</template>

<style></style>
