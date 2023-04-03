<template>
<section>
  <h1>Error 404</h1>
  <NuxtLink to="/">Home page</NuxtLink>
</section>
</template>

<script>
export default {
  props: ['error'],
  layout: 'error' // you can set a custom layout for the error page
};
</script>

<style scoped>

</style>