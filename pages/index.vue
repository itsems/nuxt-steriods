<template>
  <section class="container">
    <h1>Home Page</h1>
    <nuxt-link to="/users">Users</nuxt-link>
    
    <h2>Feature Posts</h2>
    <PostList />

    
    
  </section>
</template>

<script>

import PostList from '@/components/Posts/PostList'

export default {
  components: { PostList }
}
</script>

<style>
.container {
  text-align: center;
}

</style>
