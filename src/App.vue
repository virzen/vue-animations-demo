<template>
  <div id="app">
    <basic-transition />
    <different-durations />
    <css-animations />
    <custom-classes />
    <appear />
    <hooks />
    <in-out />
    <between-components />
    <list />
    <three-d-list />
  </div>
</template>

<script>
import BasicTransition from './components/BasicTransition.vue'
import DifferentDurations from './components/DifferentDurations.vue'
import CssAnimations from './components/CssAnimations.vue'
import CustomClasses from './components/CustomClasses.vue'
import Appear from './components/Appear.vue'
import Hooks from './components/Hooks.vue';
import InOut from './components/InOut.vue'
import BetweenComponents from './components/BetweenComponents.vue'
import List from './components/List.vue'
import ThreeDList from './components/ThreeDList.vue'

export default {
  name: 'app',
  components: {
    BasicTransition,
    DifferentDurations,
    CssAnimations,
    CustomClasses,
    Appear,
    InOut,
    BetweenComponents,
    List,
    ThreeDList,
    Hooks,
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-bottom: 200px;
}
</style>
