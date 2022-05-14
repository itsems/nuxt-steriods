<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost"  @submit="onSubmitted" />
    </section>
  </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm'
import axios from 'axios'

export default {
  layout: 'admin',
  components: { AdminPostForm },
  asyncData(context) {
    console.clear();
    console.log(context.params.postId);
    console.log('https://fir-cea85.firebaseio.com/posts/' + context.params.postId + '.json')
    return axios.get('https://fir-cea85.firebaseio.com/posts/' + context.params.postId + '.json')
            .then(res => {
              console.log('loadedPost', res.data);
              return {
                loadedPost: res.data
              }
            })
            .catch(e => context.error(e))
  },
  data() {
    return {}
  },
  methods: {
    onSubmitted(editedPost) {
      axios.put('https://fir-cea85.firebaseio.com/posts/' + this.$route.params.postId + '.json', editedPost)
            .then(res => {
              console.log('put res', res);
              this.$router.push('/admin')
              
            })
            .catch(e => context.error(e))
    }
  }
}
</script>

<style>

</style>