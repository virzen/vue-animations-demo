<template>
  <div id="demo">
    <h2>In Out</h2>
    <button @click="show = !show">Toggle</button>
    <!-- and add a mode -->
    <transition name="fade">
      <!-- remember to add keys! - past you -->
      <!-- and bind dynamic key -->
      <!-- <p :key="show"> -->
      <p v-if="show">
        <img src="../assets/logo.png" />
      </p>
      <p v-else>
        <img src="../assets/react.svg" />
      </p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'InOut',
  data: function () {
    return {
      show: true,
    }
  }
}
</script>

<style scoped>
  .fade-enter-active  {
    transition: opacity 0.5s;
  }

  .fade-enter {
    opacity: 0;
  }


  /*
  .fade-enter-active, .fade-leave-active  {
    transition: opacity 0.5s;
  }

  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
  */




  img {
    width: 200px;
    height: 200px;
  }
</style>
