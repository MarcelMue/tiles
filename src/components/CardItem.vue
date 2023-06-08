<script setup lang="ts">
import ToolingIcon from "./icons/IconTooling.vue";
</script>

<template>
  <div id="planflex">
    <transition name="flip" mode="out-in">
      <component :is="comp" width="100px" height="100px" :style="rotation" :color1="c1" :color2="c2"/>
    </transition>
  </div>
</template>

<script lang="ts">
export default {
  name: "CardItem",
  computed: {
     rotation() {
        return { transform: 'rotate('+ this.rot +')'}
     },
    c1() {
      return this.color1;
    },
    c2() {
      return this.color2;
    }
  },
  props: {
    color1: {
      type: String,
      default(){
        return "black"
      }
    },
    color2: {
      type: String,
      default(){
        return "black"
      }
    },
    rot: {
      type: String,
      default(){
        return "0 deg"
      }
    },
    comp: {
      type: Object,
      default(){
        return ToolingIcon
      }
    },
  },
};
</script>

<style>
.flip-enter-active, .flip-leave-active {
  transition: all 0.2s ease;
}

.flip-enter-from,
.flip-leave-to {
  transform: rotateY(180deg);
  opacity: 0;
}
</style>
