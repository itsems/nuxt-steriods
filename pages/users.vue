<template>
  <div>
    <h2>Users.vue</h2>

    <input type="text" v-model="userId">
    <button @click="onLoadUser">Load User</button>
    <br>
    <p>nuxt-child start here</p>
    <nuxt-child />
    <p>nuxt-child end here</p>
  </div>
</template>

<script>
export default {
  layout: 'users',
  data() {
    return {
      userId: ''
    }
  },
  methods: {
    onLoadUser() {
      this.$router.push('/users/'+this.userId)
    }
  }
}
</script>

<style>

</style>