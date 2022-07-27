<template>
  <nav class="nav_bar">
    <MenuButton @active="action" />
    <nuxt-link to="/">
      <img class="nav_bar__logo" src="~/assets/img/logo-black.svg" alt="">
    </nuxt-link>
    <ul class="nav_bar__list" :class="{'nav_bar__list-active': navBarActive}">
      <li class="nav_bar__list_item">
        <NavBarItem :pathLink="'/'" :pathName="'Главная'" />
      </li>
      <li class="nav_bar__list_item">
        <NavBarItem :pathLink="'/posts'" :pathName="'Статьи'" />
      </li>
      <li class="nav_bar__list_item">
        <NavBarItem :pathLink="'/tutorials'" :pathName="'Туториалы'" />
      </li>
      <li class="nav_bar__list_item">
        <NavBarItem :pathLink="'/news'" :pathName="'Новости'" />
      </li>
      <li class="nav_bar__list_item">
        <NavBarItem :pathLink="'/products'" :pathName="'В разработке'" />
      </li>
      <li class="nav_bar__list_item">
        <NavBarItem :pathLink="'/develop'" :pathName="'Песочница'" />
      </li>
    </ul>
  </nav>
</template>

<script>
import NavBarItem from '~/components/navigation/NavBarItem.vue';
import MenuButton from "~/components/navigation/MenuButton.vue";
export default {
  name: "NavBar",
  components: {
    NavBarItem, MenuButton
  },
  data () {
    return{
      navBarActive: false
    }
  },
  methods: {
    action (e) {
      this.navBarActive = e.active
    }
  }
}
</script>

<style lang="scss" scoped>
  @import "assets/vars";
  ul{
    list-style: none;
  }
  .nav_bar{
    display: flex;
    flex-direction: row;
    align-items: center;
    height: calc-px(88);
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    background: rgba(255, 255, 255, 0.6);
    backdrop-filter: blur(5px);
    z-index: 10;
    &__logo{
      width: calc-px(50);
    }
    &__list{
      display: flex;
      flex-direction: row;
      margin-left: calc-px(50);
      height: 100%;
      display: flex;
      flex-direction: row;
      align-items: center;
      position: absolute;
      left: calc-px(170);
      top: -100%;
      transition: .3s;
      &_item{
        height: 100%;
        position: relative;
        min-width: fit-content;
        margin-top: -100%;
        transition: .3s;
        &:nth-child(1){
          animation: removeNavItem 1s ease-in-out forwards;
        }
        &:nth-child(2){
          animation: removeNavItem 1.2s ease-in-out forwards;
        }
        &:nth-child(3){
          animation: removeNavItem 1.3s ease-in-out forwards;
        }
        &:nth-child(4){
          animation: removeNavItem 1.4s ease-in-out forwards;
        }
        &:nth-child(5){
          animation: removeNavItem 1.5s ease-in-out forwards;
        }
        &:nth-child(6){
          animation: removeNavItem 1.6s ease-in-out forwards;
        }
      }
      &-active{
        top: 0;
        transition: .3s;
        .nav_bar__list_item{
          margin-top: -100%;
          &:nth-child(1){
            animation: getNavItem 0s ease-in-out forwards;
          }
          &:nth-child(2){
            animation: getNavItem 0.2s ease-in-out forwards;
          }
          &:nth-child(3){
            animation: getNavItem 0.3s ease-in-out forwards;
          }
          &:nth-child(4){
            animation: getNavItem 0.4s ease-in-out forwards;
          }
          &:nth-child(5){
            animation: getNavItem 0.5s ease-in-out forwards;
          }
          &:nth-child(6){
            animation: getNavItem 0.6s ease-in-out forwards;
          }
        }
      }
    }
  }

  @keyframes getNavItem {
    from{
      margin-top: -100%;
    }
    to{
      margin-top: 0;
    }
  }
  @keyframes removeNavItem {
    from{
      margin-top: 0;
    }
    to{
      margin-top: -100%;
    }
  }
</style>
