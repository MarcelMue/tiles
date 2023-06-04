<script setup lang="ts">
import SupportIcon from "./icons/IconSupport.vue";
</script>

<template>
  <div id="planflex">
    <SupportIcon width="100px" height="100px" :fill="cardInfo.color"/>
  </div>
</template>

<script lang="ts">
export default {
  name: "cardBack",
  props: {
    cardInfo: {
      type: Object,
      default() {
        return {
          action_id: 2,
          actor: "Sean Connery",
          size: "md",
          color: "blue",
          style: "background-color: blue;",
        };
      },
    },
  },
  methods: {
    choose() {
      console.log("chosen");
    },
  },
};
</script>
