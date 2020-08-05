<template>
  <div id>
    <SearchBar @termChange="onTermChange"> </SearchBar>
    <VideoList/>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList'
import axios from 'axios'

const API_KEY = process.env.VUE_APP_YOUTUBE_API;

export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList
  },
  methods: {
    onTermChange(searchTerm) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
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