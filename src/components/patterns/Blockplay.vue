<script lang="ts">
export default {
  name: "Blockplay",
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
        return "white"
      }
    }
  },
  computed: {
    c1() {
      return "fill:" + this.color1;
    },
    c2() {
      return "fill:" + this.color2;
    }
  },
};
</script>

<template>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="100"
      height="100"
      viewBox="0 0 80 80"
    >
    <rect x="0" y="0" width="120" height="120" :style="c1" />
    <defs>
    <g id="brunit">
    <g transform="scale(1,-1)">
    <polygon points="0,50 0,100 50,100" :style="c2" />
    <polygon points="0,45 0,25 25,50 25,70" :style="c2" />
    <polygon points="0,20 0,0 25,25 25,45" :style="c2" />
    <polygon points="29,52 29,72 50,72" :style="c2" />
    <polygon points="29,27 29,47 50,47" :style="c2" />
    </g>
    </g>
    <g id="br2unit">
    <g transform="scale(-1,1)">
    <polygon points="0,45 0,25 25,50 25,70" :style="c2" />
    <polygon points="0,20 0,0 25,25 25,45" :style="c2" />
    <polygon points="29,52 29,72 50,72" :style="c2" />
    <polygon points="29,27 29,47 50,47" :style="c2" />
    </g>
    </g>
    </defs>
    <use x="0" y="70" xlink:href="#brunit" />
    <use x="80" y="10" xlink:href="#br2unit" />

    </svg>
  </template>