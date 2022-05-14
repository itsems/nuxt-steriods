<template>
  <div class="posts-list">
    <h1>Posts list</h1>
    <section class="featured-posts">
      <PostList :posts="loadedPosts" />
    </section>
    
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
  components: { PostList },
  created() {},
  computed: {
    loadedPosts() {
      console.log(this.$store.getters.loadedPosts);
      return this.$store.getters.loadedPosts
    }
  }
}
</script>

<style>

</style>