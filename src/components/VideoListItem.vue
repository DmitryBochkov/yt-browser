<template>
  <li class="media my-3" @click="onVideoSelect">
    <img class="mr-3" :src="thumbnailUrl" :alt="video.snippet.title">
    <div class="media-body">
      <h5 class="mt-0 mb-1">{{ video.snippet.title }}</h5>
    </div>

  </li>
</template>

<script>
  export default {
    name: 'VideoListItem',
    props: ['video'],
    computed: {
      thumbnailUrl () {
        return this.video.snippet.thumbnails.default.url
      }
    },
    methods: {
      onVideoSelect () {
        this.$emit('videoSelect', this.video)
      }
    }
  }
</script>

<style scoped>
li {
  padding: 10px;
  border: 1px solid #ddd;
  cursor: pointer;
  transition: all 0.2s ease-in-out;
}
li:hover {
  background-color: #eee;
}
</style>
