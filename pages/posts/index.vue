<template>
  <div class="posts-list">
    <h1>Posts list</h1>
    <section class="featured-posts">
      <PostList/>
    </section>
    
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
  components: { PostList }
}
</script>

<style>

</style>