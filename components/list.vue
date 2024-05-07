<template>
    <b-container fluid class="py-4">
      <b-row class="d-flex justify-content-center mb-3">
        <h2>Movie Search Results</h2>
      </b-row>
      <b-row class="d-flex flex-wrap justify-content-around">
        <b-col
          cols="12"
          md="6"
          lg="4"
          xl="3"
          v-for="movie in movies"
          :key="movie.movie_id"
          class="mb-4"
        >
          <b-card
            :title="movie.title"
            :img-src="movie.poster_image_url"
            img-alt="Movie Poster"
            img-top
            tag="article"
            class="d-flex flex-column align-items-center"
          >
            <b-card-text class="text-center mb-3">{{ movie.popularity_summary }}</b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </template>
  
  <script>
  export default {
    props: {
      movies: Array
    }
  }
  </script>
  
  <style scoped>
  /* Add custom styles or utility classes here */
  </style>
  