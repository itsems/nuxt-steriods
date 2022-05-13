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
      requied: true,
      default: 'https://lh3.googleusercontent.com/DQj-gonAVTlhj5W7_DhBVmX-0P42rfvx8TSp1WfQeZ6iFIon6InIS8M4Nbqy7Ql5ahgEXSiRDiWD88v-bcPYIEAg3Q=w640-h400-e365-rj-sc0x00ffffff'
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
.post-thumbnail {
  width: 100%;
  height: 171px;
  background-size: contain;
  background-repeat: no-repeat;
}
</style>