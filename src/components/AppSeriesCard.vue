<script>
export default {
  props: {
    title: String,
    original_title: String,
    original_language: String,
    vote_average: String,
    poster_path: String,
  },

  data() {
    return {
      lingue: ["it", "de", "en", "es", "ja", "hi", "fr"],
    };
  },
};
</script>

<template>
  <div class="card">
    <ul>
      <li v-if="poster_path">
        <img
          class="poster"
          :src="'https://image.tmdb.org/t/p/w342/' + poster_path"
          alt=""
        />
      </li>
      <li v-else>
        <img class="poster" src="../../public/nopic.jpg" alt="" />
      </li>

      <li>
        {{ title }}
      </li>
      <li>
        {{ original_title }}
      </li>
      <li v-if="lingue.includes(original_language)">
        <img
          class="flag"
          :src="'./bandiere/' + original_language + '.png'"
          alt=""
        />
      </li>
      <li>
        {{ vote_average }}
      </li>
    </ul>
  </div>
</template>

<style>
.card {
  background-color: antiquewhite;
}

li {
  list-style: none;
}
.flag {
  width: 40px;
}
</style>
