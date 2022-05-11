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
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          loadedPosts: [
            { id: '1', title: 'First Post', previewText: 'prepre', thumbnail: ''},
            { id: '2', title: '2nd Post', previewText: 'prepre2', thumbnail: ''}
          ]
        })
      }, 1000);
      // reject(new Error())
    })
    .then(data => {
      return data
    })
    .catch(e => {
      context.error(e)
    })
  },
  created() {
    this.$store.dispatch('setPosts', this.loadedPosts)
    console.log(this.$store.getters.loadedPosts);
  }
}
</script>

<style>

</style>