<template>
  <div>
    <Header/>
    <small>(Users Layout)</small>
    <nuxt/>
    <footer>Users Footer</footer>
  </div>
</template>

<script>
import Header from '~/components/Header.vue'

export default {
  components: {
    Header
  }
}
</script>


