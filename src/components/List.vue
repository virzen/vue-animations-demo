<template>
  <div id="demo">
    <h2>List</h2>
    <button @click="add">Add</button>
    <button @click="remove">Remove</button>
    <button @click="shuffle">Shuffle</button>
    <ul>
      <transition-group name="slide">
        <li v-for="item in items" :key="item.id">
          <img :src="item.src" />
        </li>
      </transition-group>
    </ul>
  </div>
</template>

<script>
import { shuffle, last } from 'lodash';
import vueLogo from '../assets/logo.png';
import reactLogo from '../assets/react.svg';

export default {
  name: 'List',
  data: function () {
    return {
      items: [
        { id: 0, src: vueLogo },
        { id: 1, src: vueLogo },
        { id: 2, src: vueLogo },
        { id: 3, src: reactLogo },
        { id: 4, src: vueLogo },
      ]
    };
  },
  methods: {
    shuffle: function () {
      this.items = shuffle(this.items)
    },
    add: function () {
      this.items.push({
        id: last(this.items).id + 1,
        src: vueLogo,
      })
    },
    remove: function () {
      this.items.splice(this.items.length - 2, 1)
    }
  }
}
</script>

<style scoped>
  .slide-enter-active, .slide-leave-active {
    transition: transform 0.5s, opacity 0.5s;
  }

  .slide-enter, .slide-leave-to /* .slide-leave-active below version 2.1.8 */ {
    transform: translateY(-30px);
    opacity: 0;
  }

  /*
  .slide-move {
    transition: transform 0.5s;
  }
  */

  /*
  .slide-leave-active {
    position: absolute;
  }
  */





  ul {
    padding: 0;
  }

  li {
    display: inline-block;
    list-style-type: none;
  }

  img {
    height: 70px;
  }
</style>
