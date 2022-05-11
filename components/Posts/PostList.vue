<template>
  <div class="post-list">
    <PostPreview :is-admin="isAdmin" id="1" thumbnail="" previewText="asdf" title="Hello" />          
    <PostPreview :is-admin="isAdmin" id="2" thumbnail="" previewText="zxcv" title="Hello 2" />          
    <PostPreview :is-admin="isAdmin" id="3" thumbnail="" previewText="qwer" title="Hello 3" />          
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
}
</style>