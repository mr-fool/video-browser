<template>
  <div id>
    <SearchBar @termChange="onTermChange"> </SearchBar>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';
import axios from 'axios'

const API_KEY = process.env.VUE_APP_YOUTUBE_API;

export default {
  name: 'App',
  components: {
    SearchBar
  },
  methods: {
    onTermChange(searchTerm) {
      axios.get('https://googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
        }
      }).then(response => console.log(response))
    }
  }

}
</script>