<template>
  <div id="demo">
    <h2>Basic transition</h2>
    <button @click="show = !show">
      Toggle
    </button>
    <button @click="showClasses = !showClasses">See the classes</button>
    <transition name="fade">
      <p v-if="show">
        <img src="../assets/logo.png" />
      </p>
    </transition>
    <transition name="fade">
      <p v-if="showClasses">
        <img src="../assets/transition.png" />
      </p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'BasicTransition',
  data: function () {
    return {
      show: true,
      showClasses: false,
    };
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
