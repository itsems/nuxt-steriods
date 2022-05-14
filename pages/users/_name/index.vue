<template>
  <div>
    <h2>user name: {{ $route.params.name }}</h2>
  </div>
</template>

<script>
export default {
  validate (data) {
    // return data.params.name === 'emma'
    return true
  }
}
</script>

<style>

</style>