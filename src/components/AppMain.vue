<script>
import AppMovieList from "./AppMovieList.vue";
import AppSeriesList from "./AppSeriesList.vue";

export default {
  data() {
    return {};
  },
  components: { AppMovieList, AppSeriesList },
};
</script>

<template>
  <main><AppMovieList /> <AppSeriesList /></main>
</template>

<style>
main {
  padding-top: 20px;
  background-image: url("/background.jpg");
  min-height: 100vh;
}
</style>
