<template>
  <div id>
    <SearchBar @termChange="onTermChange"> </SearchBar>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';

const API_KEY = process.env.VUE_APP_YOUTUBE_API;

export default {
  name: 'App',
  components: {
    SearchBar
  },
  methods: {
    onTermChange(searchTerm) {
      console.log(searchTerm)
    }
  }

}
</script>