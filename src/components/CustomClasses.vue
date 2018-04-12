<template>
  <div id="demo">
    <h2>Custom classes</h2>
    <button @click="show = !show">
      Toggle
    </button>
    <transition
      name="fade"
      enter-active-class="ill-be-back"
      leave-active-class="its-showtime"
      enter-class="hasta-la-vista-baby"
      leave-to-class="i-need-your-clothes-your-boots-and-your-motorcycle"
    >
      <p v-if="show">
        <img src="../assets/logo.png" />
      </p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'CustomClasses',
  data: function () {
    return {
      show: true,
    };
  }
}
</script>

<style scoped>
  .ill-be-back, .its-showtime {
    transition: opacity .5s;
  }

  .hasta-la-vista-baby, .i-need-your-clothes-your-boots-and-your-motorcycle {
    opacity: 0;
  }
</style>
