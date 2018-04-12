<template>
  <div id="demo">
    <h2>Transition between components</h2>
    <button @click="logo = logo == 'vue' ? 'react' : 'vue'">Toggle</button>
    <p>
      <transition name="fade" mode="out-in">
        <component :is="logo"></component>
      </transition>
    </p>
  </div>
</template>

<script>
import vueLogo from '../assets/logo.png';
import reactLogo from '../assets/react.svg';

export default {
  name: 'BetweenComponents',
  data: function () {
    return {
      logo: "vue",
    }
  },
  components: {
    "vue": {
      render: (createElement) =>
        createElement('img', {
          attrs: { src: vueLogo }
        })
    },
    "react": {
      render: (createElement) =>
        createElement('img', {
          attrs: { src: reactLogo }
        })
    },
  }
}
</script>

<style scoped>
  .fade-enter-active, .fade-leave-active  {
    transition: opacity 0.5s;
  }

  .fade-enter, .fade-leave-to {
    opacity: 0;
  }



  img {
    width: 200px;
    height: 200px;
  }
</style>
