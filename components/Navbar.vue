<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Nuxt SSR</a>


    <div class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <nuxt-link exact no-prefetch active-class="active" class="nav-link" to="/">
            <a>Home</a>
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/about">
            <a>About</a>
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/users">
            <a>Users</a>
          </nuxt-link>
        </li>
        <li class="nav-item" v-if="!hasTocken">
          <nuxt-link active-class="active" class="nav-link" to="/login">
            <a>Login</a>
          </nuxt-link>
        </li>
        <li class="nav-item" v-else>
            <a @click.prevent="logout" href="#" class="nav-link">Logout</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  computed: {
    hasTocken () {
      return this.$store.getters.hasToken
    }
  },
  methods: {
    logout () {
      this.$store.dispatch('logout')
      this.$router.push('/login')
    }
  }
}
</script>

<style scoped>

</style>
