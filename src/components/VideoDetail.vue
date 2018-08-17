<template>
  <div v-if="video">
    <div>
      <!-- <iframe width="560" height="315" src="https://www.youtube.com/embed/WQMglp-JASk" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe> -->
    </div>
    <div class="details">
      <h4>{{ video.snippet.title }}</h4>
      <p>{{ video.snippet.description }}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'VideoDetail',
    props: ['video']
  }
</script>

<style scoped>
.details {
  margin-top: 10px;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
}
</style>
