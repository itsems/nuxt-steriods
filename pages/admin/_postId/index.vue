<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost" />
    </section>
  </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm'
export default {
  layout: 'admin',
  components: { AdminPostForm },
  data() {
    return {
      loadedPost: {
        author: 'emma',
        title: 'my title',
        content: 'ddd',
        thumbnail: 'asdf'
      }
    }
  }
}
</script>

<style>

</style>