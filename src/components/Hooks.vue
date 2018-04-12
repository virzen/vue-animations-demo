<template>
  <div id="demo">
    <h2>JavaScript Hooks</h2>
    <button @click="show = !show">Toggle</button>
    <transition
      name="fade"
      @before-enter="beforeEnter"
      @enter="enter"
      @after-enter="afterEnter"
      @enter-cancelled="enterCancelled"

      @before-leave="beforeLeave"
      @leave="leave"
      @after-leave="afterLeave"
      @leave-cancelled="leaveCancelled"
    >
      <p v-if="show">
        <img src="../assets/logo.png" />
      </p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'Hooks',
  data: function () {
    return {
      show: true,
    };
  },
  methods: {
    beforeEnter: function (el) {
      alert('beforeEnter')
    },

    enter: function (el, done) {
      alert('enter');
      done();
    },

    afterEnter: function (el) {
      alert('afterEnter')
    },

    enterCancelled: function (el) {
      alert('enterCancelled')
    },

    beforeLeave: function (el) {
      alert('beforeLeave')
    },

    leave: function (el, done) {
      alert('leave')
      done()
    },

    afterLeave: function (el) {
      alert('afterLeave')
    },

    // leaveCancelled only available with v-show
    leaveCancelled: function (el) {
      alert('leaveCancelled')
    }
  }
}
</script>

<style scoped>
  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }

  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
  }
</style>
