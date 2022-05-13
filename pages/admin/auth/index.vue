<template>
  <div class="admin-auth-page">
    <div class="auth-container">
      <form @submit.prevent="onSubmit">
        <label>Email</label>
        <input type="email">
        <br>
        <label>Password</label>
        <input type="password">
        <br>
        <button type="submit" v-if="isLogin">Login</button>
        <button type="submit" v-else>Sign Up</button>
        <button @click.prevent="isLogin = !isLogin">Switch to {{ isLogin ? 'Signup' : 'Login' }}</button>

      </form>
    </div>
  </div>
  
</template>

<script>
export default {
  layout: 'admin',
  data() {
    return {
      isLogin: false
    }
  },
  methods: {
    onSubmit() {
      // this.$axios.$post()
    }
  }
}
</script>

<style scoped>
label { margin-right: 10px;}
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