<template>
  <section>
    <h1>{{pageTitle}}</h1>

    <ul>
      <li v-for="user in users" :key="user.id">
        <a href="#" @click.prevent="openUser(user.id)"> {{ user.name }}</a>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  async fetch() {
    if (this.$store.getters['users/users'].length == 0) {
      await this.$store.dispatch('users/fetch')
    }
  },
  name:'user-index',
  data: ()=>({
    pageTitle: 'Users',
  }),
  computed: {
    users() {
      return this.$store.getters['users/users']
    }
  },
  methods: {
    openUser(id) {
      this.$router.push('/users/' + id);
    },
  },
};
</script>

<style scoped>

</style>