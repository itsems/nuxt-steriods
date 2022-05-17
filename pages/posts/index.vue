<template>
  <div class="posts-list">
    <h1>Posts list</h1>
    <section class="featured-posts">
      <PostList :posts="loadedPosts" />
    </section>
    
  </div>
</template>

<script>
export default {
  created() {},
  computed: {
    loadedPosts() {
      return this.$store.getters.loadedPosts
    }
  }
}
</script>

<style>

</style>