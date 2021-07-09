<template>
  <div>
    <h1 v-html="title" />
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  props: ["title", "text"],
}
</script>

<style scoped>
  b {
    color: red!important;
  }
</style>