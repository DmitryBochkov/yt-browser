<template>
  <div class="container">
    <search-bar @termChange="onTermChange"></search-bar>
    <video-detail :video="selectedVideo"></video-detail>
    <video-list :videos="videos" @videoSelect="onVideoSelect"></video-list>
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from './components/SearchBar.vue'
import VideoList from './components/VideoList.vue'
import VideoDetail from './components/VideoDetail.vue'
const API_KEY = 'AIzaSyC6bssaWdZl2lzOIXy-aGGC_86-gV-GwAs'

export default {
  name: 'App',
  data () {
    return {
      videos: [],
      selectedVideo: null
    }
  },
  components: {
    SearchBar,
    VideoList,
    VideoDetail
  },
  methods: {
    onTermChange (searchTerm) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
        }
      })
        .then(response => {
          this.videos = response.data.items
        })
    },
    onVideoSelect (video) {
      this.selectedVideo = video
    }
  }
}
</script>

<style scoped>
</style>
