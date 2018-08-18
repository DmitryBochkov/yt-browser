<template>
  <div class="input-group pt-3 mb-3">
    <input type="text" @input="onInput" class="form-control" placeholder="Search for Youtube videos">
    <div class="input-group-append">
      <button class="btn btn-outline-secondary" type="button">Search</button>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'SearchBar',
    methods: {
      onInput (event) {
        this.$emit('termChange', event.target.value)
      }
    }
  }
</script>

<style scoped>
</style>
