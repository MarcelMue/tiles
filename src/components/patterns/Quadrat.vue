<script lang="ts">
export default {
  name: "Quadrat",
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
  <defs>
    <g id="unit">
      <polygon points="0,50 25,50 0,25" />
      <polygon points="50,50 25,25 50,25" />
      <polygon points="25,25 25,0 0,0" />
    </g>
  </defs>
  <rect x="0" y="0" width="50" height="50" :style="c1" />
  <use x="0" y="0" xlink:href="#unit"  :style="c2"/>
  <rect x="0" y="50" width="50" height="50" :style="c2" />
  <use x="0" y="50" xlink:href="#unit" :style="c1"/>
  <rect x="50" y="0" width="50" height="50" :style="c2" />
  <use x="50" y="0" xlink:href="#unit" :style="c1"/>
  <rect x="50" y="50" width="50" height="50" :style="c1" />
  <use x="50" y="50" xlink:href="#unit" :style="c2"/>

  </svg>
</template>
