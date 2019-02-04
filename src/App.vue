<template>
  <div class="container text-center pt-5">
    <button class="btn btn-primary mb-5" @click="show = !show">Toggle</button>

    <p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consectetur, saepe?</p>
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

</style>
