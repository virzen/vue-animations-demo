<template>
  <div id="demo">
    <h2>CSS Animations</h2>
    <button @click="show = !show">
      Toggle
    </button>
    <transition name="bounce">
      <p v-if="show">
        <img src="../assets/logo.png" />
      </p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'CssAnimations',
  data: function () {
    return {
      show: true,
    };
  }
}
</script>

<style scoped>
  /* bounce-enter removed on animationend instead of after one frame */
  .bounce-enter-active {
    animation: bounce-in .5s;
  }

  .bounce-leave-active {
    animation: bounce-in .5s reverse;
  }

  @keyframes bounce-in {
    0% {
      transform: scale(0);
    }
    50% {
      transform: scale(1.5);
    }
    100% {
      transform: scale(1);
    }
  }
</style>
