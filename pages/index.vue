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
  asyncData(context, cb) {
    console.log(context);
    setTimeout(() => {
      cb(null, {
        loadedPosts: [
          { id: '1', title: 'First Post', previewText: 'prepre', thumbnail: ''},
          { id: '2', title: '2nd Post', previewText: 'prepre2', thumbnail: ''}
        ]})
    }, 1500);
  },
  created() {
   
  }
}
</script>

<style>
.container {
  text-align: center;
}

</style>
