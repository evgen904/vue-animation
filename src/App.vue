<template>
  <div class="container text-center pt-5">
    <button class="btn btn-primary mb-5" @click="show = !show">Toggle</button>

    <transition name="ma">
      <p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consectetur, saepe?</p>
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

  .ma-enter {}
  .ma-enter-active {}
  .ma-enter-to {}

  .ma-leave {}
  .ma-leave-active {}
  .ma-leave-to {}

</style>
