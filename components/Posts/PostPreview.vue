<template>
  <nuxt-link :to="postLink">
    <article class="post-preview">
      <div class="post-thumbnail"
        :style="{backgroundImage: `url(${thumbnail})`}"></div>
      <div class="post-content">
        PostID: {{ id }}
        <h1>Title: {{ title }}</h1>
        <p>Preview Text: {{ previewText }} </p>
      </div>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  name: 'PostPreview',
  props: {
    id: {
      type: String,
      requied: true
    },
    title: {
      type: String,
      requied: true
    },
    previewText: {
      type: String,
      requied: true
    },
    thumbnail: {
      type: String,
      requied: true
    },
    isAdmin: {
      type: Boolean,
      required: true
    }
  },
  computed: {
    postLink() {
      return this.isAdmin ? '/admin/' + this.id : '/posts/'+ this.id 
    }
  }
}
</script>

<style scoped>

.post-preview {
  border: 1px solid #555;
  text-decoration: none;
  color: #111;
  margin-bottom: 15px;
  padding: 1rem;
  margin: 0 5px;
}
</style>