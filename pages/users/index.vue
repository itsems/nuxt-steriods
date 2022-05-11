<template>
  <div>
    <h3>users index: enter id and click button</h3>
  </div>
</template>

<script>
export default {
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