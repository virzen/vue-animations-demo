<template>
  <div id="demo">
    <h2>Different durations for enter and leave</h2>
    <button v-on:click="show = !show">
      Toggle
    </button>
    <transition name="fade">
      <p v-if="show">
        <img src="../assets/logo.png" />
      </p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'SingleElementTransition',
  data: function () {
    return {
      show: true,
    };
  }
}
</script>

<style scoped>
  .fade-enter-active  {
    transition: opacity 0.2s;
  }

  .fade-leave-active {
    transition: opacity 1.5s ease-in;
  }

  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
  }
</style>
