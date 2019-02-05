<template>
  <div class="container text-center pt-5">
    <button class="btn btn-primary mb-5" @click="show = !show">Toggle</button>

    <!--<transition-->
      <!--name="ma"-->
      <!--:duration="{enter: 1500, leave: 2000}"-->
      <!--appear-->
    <!--&gt;-->
      <!--<p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consectetur, saepe?</p>-->
    <!--</transition>-->

    <!--<transition-->
      <!--enter-active-class="animated wobble"-->
      <!--leave-active-class="animate shake"-->
    <!--&gt;-->
      <!--<p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur, laborum?</p>-->
    <!--</transition>-->

    <!--<transition name="ma" mode="in-out">-->
      <!--<div class="alert alert-success" v-if="show" key="success">Success</div>-->
      <!--<div class="alert alert-danger" v-else key="danger">danger</div>-->
    <!--</transition>-->

    <transition name="ma" mode="out-in">
      <div class="alert alert-success" v-if="show" key="success">Success</div>
      <div class="alert alert-danger" v-else key="danger">danger</div>
    </transition>

  </div>
</template>

<script>
export default {
  data () {
    return {
      show: false
    }
  }
}
</script>

<style>

  .ma-enter {
    opacity: 0;
  }
  .ma-enter-active {
    transition: opacity 1s;
  }
  .ma-enter-to {}

  .ma-leave {}
  .ma-leave-active {
    animation: 1s ma-slide forwards;
    transition: opacity 1.5s;
  }
  .ma-leave-to {
    opacity: 0;
  }

  @keyframes ma-slide {
    from {
      transform: translateX(0px);
    }
    to {
      transform: translateX(-100px);
    }
  }

</style>
