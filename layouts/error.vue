<template>
  <section>
    <h1 class="error">Error 404</h1>

    <nuxt-link to="/"><a>Home</a></nuxt-link>
  </section>
</template>

<script>
export default {

}
</script>

<style scoped>
  section {
    width: 600px;
    margin: 0 auto;
    padding-top: 5rem;
  }

  h1 {
    color: red;
  }
</style>
