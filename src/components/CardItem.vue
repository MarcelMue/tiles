<script setup lang="ts">
import ToolingIcon from "./icons/IconTooling.vue";
</script>

<template>
  <div id="planflex">
    <transition name="flip" mode="out-in">
      <component :is="comp" width="100px" height="100px" :fill="color"/>
    </transition>
  </div>
</template>

<script lang="ts">
export default {
  name: "CardItem",
  props: {
    color: String,
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
