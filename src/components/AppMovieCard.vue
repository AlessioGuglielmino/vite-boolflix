<script>
export default {
  props: {
    title: String,
    original_title: String,
    original_language: String,
    vote_average: String,
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
      <li>
        {{ original_language }}
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
</style>
