<template>
  <button class="menu_btn" :class="{'menu_btn-active': active}" v-model:active="active" @click="switchActive">
    <div class="menu_btn__item" />
    <div class="menu_btn__item" />
  </button>
</template>

<script>
export default {
  name: "MenuButton",
  data () {
    return{
      active: false
    }
  },
  methods: {
    switchActive () {
      this.active = !this.active
      this.$emit('active', {
        active: this.active
      })
    }
  }
}
</script>

<style lang="scss" scoped>
  .menu_btn{
    width: 88px;
    height: 88px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
    border: 0;
    background: transparent;
    cursor: pointer;
    &:hover{
      .menu_btn__item{
        background: #CB5F12;
        transition: .2s;
      }
    }
    &__item{
      width: 35px;
      height: 4px;
      border-radius: 10px;
      background: #000;
      position: absolute;
      transition: .2s;
      &:first-child{
        transform: rotate(0deg);
        bottom: 55%;
      }
      &:last-child{
        transform: rotate(0deg);
        top: 55%;
      }
    }
    &-active{
      .menu_btn__item{
        &:first-child{
          transform: rotate(45deg);
          bottom: 48%;
        }
        &:last-child{
          transform: rotate(-45deg);
          top: 48%;
        }
      }
    }
  }
</style>
