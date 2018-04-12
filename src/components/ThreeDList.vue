<template>
  <div id="demo">
    <h2>List</h2>
    <button @click="add">Add</button>
    <button @click="remove">Remove</button>
    <button @click="shuffle">Shuffle</button>
    <transition-group name="slide" tag="ul">
      <li v-for="item in items" :key="item.id">
        <img :src="item.src" />
      </li>
    </transition-group>
  </div>
</template>

<script>
import { shuffle, max, property } from 'lodash';
import vueLogo from '../assets/logo.png';
import reactLogo from '../assets/react.svg';

export default {
  name: 'List',
  data: function () {
    return {
      items: [
        { id: 10, src: vueLogo },
        { id: 11, src: vueLogo },
        { id: 12, src: vueLogo },
        { id: 13, src: reactLogo },
        { id: 14, src: vueLogo },
        { id: 15, src: vueLogo },
        { id: 16, src: vueLogo },
        { id: 17, src: vueLogo },
        { id: 18, src: vueLogo },
      ]
    };
  },
  methods: {
    shuffle: function () {
      this.items = shuffle(this.items)
    },
    add: function () {
      this.items.push({
        id: max(this.items.map(property('id'))) + 1,
        src: vueLogo,
      })
    },
    remove: function () {
      this.items.splice(this.items.length - 1, 1)
    }
  }
}
</script>

<style scoped>
  .slide-enter-active, .slide-leave-active {
    transition: transform 0.5s, opacity 0.5s;
  }

  .slide-enter, .slide-leave-to /* .slide-leave-active below version 2.1.8 */ {
    transform: translateX(-30px);
    opacity: 0;
  }

  .slide-move {
    transition: transform 0.5s;
  }


  ul {
    padding: 0;
    display: grid;
    width: calc(70px * 3);
    height: calc(70px * 3);
    grid-template-rows: 1fr 1fr 1fr;
    grid-template-columns: 1fr 1fr 1fr;
    margin: 0 auto;
  }

  li {
    list-style-type: none;
  }

  img {
    height: 70px;
  }
</style>
