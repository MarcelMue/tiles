<script setup lang="ts">
import ToolingIcon from "./icons/IconTooling.vue";
</script>

<template>
  <div id="planflex">
    <ToolingIcon width="100px" height="100px" :fill="cardInfo.color"/>
  </div>
</template>

<script lang="ts">
export default {
  name: "cardFront",
  props: {
    cardInfo: {
      type: Object,
      default() {
        return {
          action_id: 0,
          actor: "Buster Keaton",
          size: "lg",
          color: "red",
          style: "background-color: red;",
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
