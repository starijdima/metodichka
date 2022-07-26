<template>
  <div>
    <img class="right-bg" src="../assets/img/mainpage/right-bg.png" alt="">
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NavBar from '../components/navigation/NavBar.vue';

export default Vue.extend({
  name: 'IndexPage',
  components: {
    NavBar
  },
  data () {
    return {
    }
  },
  mounted () {

  }
})
</script>

<style lang="scss" scoped>
  .right-bg{
    position: absolute;
    right: -50%;
    top: -50%;
    opacity: 0;
    animation: rightBg 1.5s .1s ease-in-out forwards;
  }

  @keyframes rightBg {
    from{
      top: -50%;
      right: -50%;
      opacity: 0;
    }
    to{
      top: 0;
      right: 0;
      opacity: 1;
    }
  }
</style>
