<template>
  <div class="container">
    <SearchBar @termChange="onTermChange"> </SearchBar>
    <div class="row">
      <VideoDetail :video="selectedVideo" />
      <VideoList @videoSelect="onVideoSelect" :videos="videos"/>
    </div>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList'
import VideoDetail from './components/VideoDetail'
import axios from 'axios'

const API_KEY = process.env.VUE_APP_YOUTUBE_API;

export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList,
    VideoDetail
  },
  data() {
    return {
      videos: [],
      selectedVideo: null
    };
  },
  methods: {
    onVideoSelect(video) {
     this.selectedVideo = video
    },
    onTermChange(searchTerm) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
        }
      }).then(response => {

        this.videos = response.data.items
      })
    }
  }

}
</script>