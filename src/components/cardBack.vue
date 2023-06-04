<template>
  <div id="planflex" :style="cardInfo.style">
    <div class="block">
      <h2>{{ cardInfo.action_id }}</h2>
    </div>
    <div class="block" :id="cardInfo.action_id" @click="choose()">
      <h3>{{ cardInfo.actor }}</h3>
    </div>
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
          color: "green",
          style: "",
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
