<template>
  <div class="admin-page">
    <section class="new-post">
      <button @click="$router.push('/admin/new-post')">Create Post</button>
      <button @click="onLogout">Logout</button>
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
  middleware: ['check-auth', 'auth'],
  components: { PostList },
  computed: {
    loadedPosts() {
      return this.$store.getters.loadedPosts
    }
  },
  methods: {
    onLogout() {
      this.$store.dispatch('logout')
      this.$router.push('/admin/auth')
    }
  }
}
</script>

<style scoped>
.admin-page {
  text-align: center;
}

</style>