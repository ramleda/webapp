<template>
  <div class="d-flex flex-column align-items-center py-4">
    <!-- Container wrapping both SearchBar and MovieList -->
    <div class="w-70">
      <SearchBar @search="fetchMovies" />
      <MovieList :movies="movies" />
    </div>
  </div>
</template>

<script>
import SearchBar from '~/components/search.vue';
import MovieList from '~/components/list.vue';

export default {
  components: {
    SearchBar,
    MovieList
  },
  data() {
    return {
      movies: []
    };
  },
  methods: {
    async fetchMovies(query) {
      try {
        const response = await this.$axios.$get(`/movies/search?query=${query}`);
        this.movies = response;
      } catch (error) {
        console.error('Error fetching movies:', error);
        this.movies = [];
      }
    }
  }
}
</script>

<style scoped>
/* Custom width class for the container to set it to 70% of the screen */
.w-70 {
  width: 70%;
  margin: auto;
}
</style>
