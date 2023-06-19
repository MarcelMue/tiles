<script lang="ts">
export default {
  name: "Janein",
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
    viewBox="0 0 240 240"
  >
  <rect x="0" y="0" width="240" height="240" :style="c1" />
  <defs>
  <g id="janeinunit">
  <polygon points="0,0 0,20 60,20 60,-20 40,-20 40,0" />
  </g>
  </defs>
  <use x="-20" y="-20" xlink:href="#janeinunit" :style="c2" />
  <use x="20" y="20" xlink:href="#janeinunit" :style="c2" />
  <use x="-20" y="60" xlink:href="#janeinunit" :style="c2" />
  <use x="20" y="100" xlink:href="#janeinunit" :style="c2" />
  <use x="-20" y="140" xlink:href="#janeinunit" :style="c2" />
  <use x="20" y="180" xlink:href="#janeinunit" :style="c2" />
  <use x="-20" y="220" xlink:href="#janeinunit" :style="c2" />
  <use x="60" y="-20" xlink:href="#janeinunit" :style="c2" />
  <use x="100" y="20" xlink:href="#janeinunit" :style="c2" />
  <use x="60" y="60" xlink:href="#janeinunit" :style="c2" />
  <use x="100" y="100" xlink:href="#janeinunit" :style="c2" />
  <use x="60" y="140" xlink:href="#janeinunit" :style="c2" />
  <use x="100" y="180" xlink:href="#janeinunit" :style="c2" />
  <use x="60" y="220" xlink:href="#janeinunit" :style="c2" />
  <use x="140" y="-20" xlink:href="#janeinunit" :style="c2" />
  <use x="180" y="20" xlink:href="#janeinunit" :style="c2" />
  <use x="140" y="60" xlink:href="#janeinunit" :style="c2" />
  <use x="180" y="100" xlink:href="#janeinunit" :style="c2" />
  <use x="140" y="140" xlink:href="#janeinunit" :style="c2" />
  <use x="180" y="180" xlink:href="#janeinunit" :style="c2" />
  <use x="140" y="220" xlink:href="#janeinunit" :style="c2" />
  <use x="220" y="-20" xlink:href="#janeinunit" :style="c2" />
  <use x="260" y="20" xlink:href="#janeinunit" :style="c2" />
  <use x="220" y="60" xlink:href="#janeinunit" :style="c2" />
  <use x="260" y="100" xlink:href="#janeinunit" :style="c2" />
  <use x="220" y="140" xlink:href="#janeinunit" :style="c2" />
  <use x="260" y="180" xlink:href="#janeinunit" :style="c2" />
  <use x="220" y="220" xlink:href="#janeinunit" :style="c2" />
  <use x="300" y="-20" xlink:href="#janeinunit" :style="c2" />
  <use x="340" y="20" xlink:href="#janeinunit" :style="c2" />
  <use x="300" y="60" xlink:href="#janeinunit" :style="c2" />
  <use x="340" y="100" xlink:href="#janeinunit" :style="c2" />
  <use x="300" y="140" xlink:href="#janeinunit" :style="c2" />
  <use x="340" y="180" xlink:href="#janeinunit" :style="c2" />
  <use x="300" y="220" xlink:href="#janeinunit" :style="c2" />
  </svg>
</template>
