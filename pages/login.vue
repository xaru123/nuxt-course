<template>
  <section>
    <div v-if="$route.query.message" class="alert alert-danger mb-3">
      Need login first
    </div>
    <form @submit.prevent="onSubmit">
      <h1>Login page</h1>
      <div class="form-group">
        <input type="text" class="form-control">
      </div>

      <p>
        <NuxtLink to="/">To home page</NuxtLink>
      </p>

      <button class="btn btn-primary" type="submit">Login</button>
    </form>
  </section>
</template>

<script>
export default {
  layout: 'empty',
  name: 'login',
  methods: {
    onSubmit() {
      this.$store.dispatch('login')
      this.$router.push('/')
    }
  }
};
</script>

<style scoped>
form {
  width: 500px;
}
</style>