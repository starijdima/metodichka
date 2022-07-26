<template>
  <div>
    <NavBar />
    <nuxt />
  </div>
</template>

<script>
import NavBar from '../components/navigation/NavBar.vue';

export default {
  name: "default",
  components: {
    NavBar
  }
}
</script>

<style scoped>

</style>
