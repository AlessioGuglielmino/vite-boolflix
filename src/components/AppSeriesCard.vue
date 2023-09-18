<script>
export default {
  props: {
    title: String,
    original_title: String,
    original_language: String,
    vote_average: String,
    poster_path: String,
    overview: String,
  },

  data() {
    return {
      lingue: ["it", "de", "en", "es", "ja", "hi", "fr"],
    };
  },
};
</script>

<template>
  <div class="flip-card">
    <div class="flip-card-inner">
      <div class="flip-card-front">
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
        </ul>
      </div>
      <div class="flip-card-back">
        <ul>
          <li>Titolo : {{ title }}</li>
          <li>Titolo Originale : {{ original_title }}</li>
          <li v-if="lingue.includes(original_language)">
            <img
              class="flag"
              :src="'./bandiere/' + original_language + '.png'"
              alt=""
            />
          </li>
          <li v-for="">
            <!-- <font-awesome-icon icon="fa-regular fa-star" />
            <font-awesome-icon icon="fa-solid fa-star" /> -->

            {{ vote_average }}
          </li>

          <li>Overview : {{ overview }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.flip-card {
  background-color: transparent;
  width: 400px;
  height: 500px;
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden; /* Safari */
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  background-color: rgb(10, 7, 20);
  color: white;
  width: 100%;
  height: 100%;
}

/* Style the back side */
.flip-card-back {
  background-color: rgb(10, 7, 20);
  color: white;
  transform: rotateY(180deg);
  padding: 1rem;
  overflow: auto;
}

/* width */
::-webkit-scrollbar {
  width: 10px;
}

/* Track */
::-webkit-scrollbar-track {
  background: black;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #e50914;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: e50914;
}

ul {
  padding: 1rem;
  height: 500px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex-direction: column;
  gap: 10px;
}

li {
  list-style: none;
}
.flag {
  width: 40px;
}
</style>
