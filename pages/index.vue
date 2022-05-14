<template>
  <section class="container">
    <h1>Home Page</h1>
    <nuxt-link to="/users">Users</nuxt-link>
    
    <h2>Feature Posts</h2>
    <PostList :posts="loadedPosts" />

  </section>
</template>

<script>

import PostList from '@/components/Posts/PostList'

export default {
  components: { PostList },
  created() { },
  computed: {
    loadedPosts() {
      return this.$store.getters.loadedPosts
    }
  }
}
</script>

<style>
.container {
  text-align: center;
}

</style>
