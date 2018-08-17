<template>
  <div>
    <ul class="list-unstyled">
      <video-list-item
        v-for="video in videos"
        :key="video.etag"
        :video="video"
        @videoSelect="onVideoSelect"
      ></video-list-item>
    </ul>
  </div>
</template>

<script>
  import VideoListItem from './VideoListItem.vue'
  export default {
    name: 'VideoList',
    props: ['videos'],
    components: {
      VideoListItem
    },
    methods: {
      onVideoSelect (video) {
        this.$emit('videoSelect', video)
      }
    }
  }
</script>

<style scoped>
</style>
