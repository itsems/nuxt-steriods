<template>
  <div class="single-post-page">
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
  asyncData(context, cb) {
    setTimeout(() => {
      cb(null, {
        loadedPost: { 
          id: '1', 
          title: 'Firs t Post (ID: ' + context.route.params.id + ")", 
          updatedDate: new Date(),
          author: 'emma',
          content: 'zxcvadfqwer',
          previewText: 'prepre', 
          thumbnail: ''
        }
      })
    }, 1000);
  }
}
</script>

<style>

</style>