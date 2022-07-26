<template>
  <nuxt-link class="nav_bar__list_item__link" :to="pathLink">
    {{ pathName }}
  </nuxt-link>
</template>

<script>
export default {
  name: "NavBarItem",
  props: {
    pathLink: {
      type: String,
      default: '/'
    },
    pathName: {
      type: String,
      default: 'Link'
    }
  }
}
</script>

<style lang="scss" scoped>
  .nav_bar__list_item__link{
    color: #000;
    transition: .2s;
    height: 100%;
    padding: 0 20px;
    font-size: 20px;
    font-weight: 400;
    display: flex;
    align-items: center;
    justify-content: center;
    &:hover{
      color: #CB5F12;
      transition: .2s;
    }
  }
</style>
