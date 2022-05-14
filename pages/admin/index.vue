<template>
  <div class="admin-page">
    <section class="new-post">
      <button @click="$router.push('/admin/new-post')">Create Post</button>
    </section>
    <section class="existing-posts">
      <h1>Existing Posts</h1>
      <PostList isAdmin :posts="loadedPosts" />
    </section>
  </div>
  
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
  layout: 'admin',
  components: { PostList },
  computed: {
    loadedPosts() {
      console.log(this.$store.getters.loadedPosts);
      return this.$store.getters.loadedPosts
    }
  },
  methods: {
    
  }
}
</script>

<style scoped>
.admin-page {
  text-align: center;
}

</style>