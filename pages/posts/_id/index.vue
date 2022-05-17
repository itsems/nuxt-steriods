<template>
  <div class="single-post-page">
      <p>post id page</p>
    <section class="post">
      <h1 class="post-title">Title of the post: {{ loadedPost.title }}</h1>
      <h2>{{ loadedPost.previewText }}</h2>
      <p>updated on {{ loadedPost.updatedDate }}</p>
      <p>Writteb by {{ loadedPost.author }}</p>
      <div class="post-details">
        <h3>Content</h3>
        <p>{{ loadedPost.content }}</p>
      </div>
    </section>
    <section class="post-feedback">
      <p>send mail to me</p>
    </section>
  </div>
</template>

<script>
export default {
  asyncData(context) {
    if (context.payload) {
      return {
        loadedPost: context.payload.postData
      }
    }
    return context.app.$axios.$get('/posts/' + context.params.id + '.json')
      .then(data => {
        return {
          loadedPost: data
        }
      })
      .catch(e => context.error(e))
  },
};
</script>

<style>

</style>