<template>
  <b-form @submit.prevent="searchMovies">
    <!-- Title Row -->
        <b-row class="d-flex justify-content-center align-items-center mb-3">
      <!-- Movie Icon or Logo -->
      <img src="apple-touch-icon.png" alt="Movies Icon" width="40" height="40" class="mr-2"/>
      <!-- Title -->
      <h2>Search Movies</h2>
    </b-row>
    <b-input-group>
      <b-form-input v-model="searchQuery" placeholder="Search for movies..."></b-form-input>
      <b-input-group-append>
        <b-button type="submit" variant="primary">Search</b-button>
      </b-input-group-append>
    </b-input-group>
  </b-form>
</template>

<script>
export default {
  data() {
    return {
      searchQuery: ''
    };
  },
  methods: {
    searchMovies() {
      this.$emit('search', this.searchQuery);
    }
  }
}
</script>
