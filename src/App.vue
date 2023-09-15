<script>
import { store } from "./data/store";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

import axios from "axios";

export default {
  data() {
    return {
      store,
    };
  },
  // COMPONENTS
  components: { AppHeader, AppMain },

  // METODI
  methods: {
    fetchMovie(endpoint) {
      axios.get(endpoint).then((response) => {
        this.store.Movies = response.data.results;
      });
    },
    fetchSeries(endpoint) {
      axios.get(endpoint).then((response) => {
        this.store.Series = response.data.results;
        console.log(this.store.Series);
      });
    },

    filterMovie(elementSearch) {
      const customUrl = this.store.apiUri + elementSearch + this.store.apiKey;
      this.fetchMovie(customUrl);
    },

    filterSeries(elementSearch) {
      const customUrl =
        this.store.apiUriSeries + elementSearch + this.store.apiKey;
      this.fetchSeries(customUrl);
    },
  },
};
</script>

<template>
  <AppHeader @form-input="filterMovie" @form-input-series="filterSeries" />
  <AppMain />
</template>

<style></style>
