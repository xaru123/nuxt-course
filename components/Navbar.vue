<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Nuxt SSR App</a>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <NuxtLink
                exact
                no-prefetch
                active-class="active"
                class="nav-link"
                to="/">Home
            </NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink
                no-prefetch
                active-class="active"
                class="nav-link"
                to="/about">About
            </NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink
                no-prefetch
                active-class="active"
                class="nav-link"
                to="/users">Users
            </NuxtLink>
          </li>
          <li class="nav-item" v-if="!hasToken">
            <NuxtLink
                no-prefetch
                active-class="active"
                class="nav-link"
                to="/login">Login
            </NuxtLink>
          </li>
          <li class="nav-item" v-else>
            <a
               href="#" class="nav-link" @click.prevent="onLogout">Logout
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  computed: {
    hasToken () {
      return this.$store.getters.hasToken
    }
  },
  methods: {
    onLogout() {
      this.$store.dispatch('logout')
      this.$router.push('/login')
    }
  }
};
</script>

<style scoped>

</style>