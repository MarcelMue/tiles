<script lang="ts">
export default {
  name: "Pantheon",
  computed: {
    c1() {
      return "fill:" + this.color1;
    },
    c2() {
      return "fill:" + this.color2;
    }
  },
  props: {
    color1: {
      type: String,
      default(){
        return "blue"
      }
    },
    color2: {
      type: String,
      default(){
        return "black"
      }
    }
  },
};
</script>

<template>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    width="100"
    height="100"
    viewBox="0 0 100 100"
  >
  <rect x="0" y="0" width="100" height="100" :style="c1" />
  <defs>
    <g id="pantheonunit">
      <polygon points="0,0 0,50 50,50 50,0" :style="c2" />
      <polygon points="5,5 5,45 45,45 45,5" :style="c1" />
      <polygon points="10,10 10,40 40,40 40,10" :style="c2" />
      <polygon points="15,15 15,45 45,45 45,15" :style="c1" />
    </g>
  </defs>
  <use x="0" y="0" xlink:href="#pantheonunit" />
  <use x="0" y="50" xlink:href="#pantheonunit" />
  <use x="50" y="0" xlink:href="#pantheonunit" />
  <use x="50" y="50" xlink:href="#pantheonunit" />

  </svg>
</template>
