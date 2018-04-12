<template>
  <div id="demo">
    <h2>Appear</h2>
    <transition name="fade" appear>
      <img src="../assets/logo.png" />
    </transition>
  </div>
</template>

<script>
export default {
  name: 'Appear',
}
</script>

<style scoped>
  .fade-enter-active {
    transition: opacity 1s;
  }

  .fade-enter {
    opacity: 0;
  }
</style>
