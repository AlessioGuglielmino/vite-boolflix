<script>
import { store } from "./data/store";
import AppHeader from "./components/AppHeader.vue";

export default {
  data() {
    return {
      store,
    };
  },
  methods: {},

  components: { AppHeader },
};
</script>

<template>
  <AppHeader />
</template>

<style></style>
