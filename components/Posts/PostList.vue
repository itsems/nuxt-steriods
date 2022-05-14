<template>
  <div class="post-list">
    <PostPreview
      class="each-post"
      v-for="post in posts"
      :key="post.id"
      :id="post.id"
      :is-admin="isAdmin"
      :thumbnail="post.thumbnail"
      :title="post.title"
      :previewText="post.previewText"
      />
  </div>
</template>

<script>
import PostPreview from '@/components/Posts/PostPreview'

export default {
  components: { PostPreview },
  props: {
    isAdmin: {
      type: Boolean,
      default: false
    },
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.post-list {
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}
.each-post {
  width: 320px;
  margin-bottom: 10px;
}
</style>