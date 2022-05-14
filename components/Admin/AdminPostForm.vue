<template>
  <form @submit.prevent>
    <label>author: </label>
    <input type="text" v-model="editedPost.author">
    <br>
    <label>title: </label>
    <input type="text" v-model="editedPost.title">
    <br>
    <label>content: </label>
    <input type="text" v-model="editedPost.content">
    <br>
    <label>previewText: </label>
    <input type="text" v-model="editedPost.previewText">
    <br>
    <button @click="onCancel">Cancel</button>
    <button @click="onSave">Save</button>
  </form>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      require: false
    }
  },
  data() {
    return {
      editedPost: this.post 
        ? { ...this.post } 
        : {
            author: '',
            title: '',
            content: '',
            previewText: ''
          }
    }
  },
  methods: {
    onSave() {
      // save
      // console.log(this.editedPost);
      this.$emit('submit', this.editedPost)
    },
    onCancel() {
      // navigate back
      this.$router.push('/admin')
    }
  }
}
</script>

<style scoped>
  input {
    margin-bottom: 15px;
  }
  form {
    margin: 10px 0;
  }
  button {
    margin: 0 5px;
  }

</style>