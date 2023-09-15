<script>
export default {
  props: {
    title: String,
    original_title: String,
    original_language: String,
    vote_average: String,
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
      <li>
        {{ title }}
      </li>
      <li>
        {{ original_title }}
      </li>
      <li v-if="lingue.includes(original_language)">
        <img :src="'./bandiere/' + original_language + '.png'" alt="" />
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
img {
  width: 30px;
}
</style>
