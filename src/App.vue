<script>
import { store } from "./data/store";
import AppHeader from "./components/AppHeader.vue";
import axios from "axios";

export default {
  data() {
    return {
      store,
    };
  },

  methods: {
    fetchCard(endpoint) {
      axios.get(endpoint).then((response) => {
        this.store.Movies = response.data.results;
        console.log(this.store.Movies);
      });
    },

    filter(elementSearch) {
      const customUrl = this.store.apiUri + elementSearch + this.store.apiKey;
      console.log(customUrl);
      this.fetchCard(customUrl);
    },
  },

  components: { AppHeader },
};
</script>

<template>
  <AppHeader @form-input="filter" />
</template>

<style></style>
