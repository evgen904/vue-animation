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

    <!--<transition name="ma" mode="out-in">-->
      <!--<div class="alert alert-success" v-if="show" key="success">Success</div>-->
      <!--<div class="alert alert-danger" v-else key="danger">danger</div>-->
    <!--</transition>-->

    <transition
      @before-enter="beforeEnter"
      @enter="enter"
      @after-enter="afterEnter"
      @enter-cancelled="enterCancelle"

      @before-leave="beforeLeave"
      @leave="leave"
      @after-leave="afterLeave"
      @leave-cancelled="leaveCancelle"
    >
      <p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta, repudiandae?</p>
    </transition>

    <br><br>

    <button class="btn btn-success" @click="add">Add</button>
    <button class="btn btn-danger" @click="remove">Remove</button>

    <hr>

    <transition-group class="list-group width300" tag="ul" name="ma2">
      <li class="list-group-item" v-for="item of items" :key="item">{{item}}</li>
    </transition-group>


  </div>
</template>

<script>
export default {
  data () {
    return {
      show: false,
      items: [1, 2, 3, 4, 5],
      nextNum: 6
    }
  },
  methods: {
    beforeEnter(el) {
      console.log('beforeEnter')
    },
    enter(el, done) {
      console.log('enter')
      done()
    },
    afterEnter(el) {
      console.log('afterEnter')
    },
    enterCancelle(el) {
      console.log('enterCancelle')
    },
    beforeLeave(el) {
      console.log('beforeLeave')
    },
    leave(el, done) {
      console.log('leave')
      done()
    },
    afterLeave(el) {
      console.log('afterLeave')
    },
    leaveCancelle(el) {
      console.log('leaveCancelle')
    },
    getIndex() {
      return Math.floor(Math.random() * this.items.length)
    },
    add() {
      this.items.splice(this.getIndex(), 0, this.nextNum++)
    },
    remove() {
      this.items.splice(this.getIndex(), 1)
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

  .width300 {
    width: 300px;
    margin: 0 auto;
  }


  .ma2-enter-active, .ma2-leave-active {
    transition: 1s all;
  }
  .ma2-enter, .ma2-leave-to {
    transform: translateX(-100px);
  }




</style>
