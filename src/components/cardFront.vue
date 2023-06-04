<script lang="ts">
import toolingIcon from "./icons/IconTooling.vue";

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
          style: "",
        };
      },
    },
  },
  components: { toolingIcon },
  methods: {
    choose() {
      console.log("chosen");
    },
  },
};
</script>

<template>
  <div id="planflex" :style="cardInfo.style">
    <div class="block">
      <h2>{{ cardInfo.action_id }}asdasd</h2>
      <figure>
        <toolingIcon width="100px" height="100px"/>
      </figure>
    </div>
    <div class="block" :id="cardInfo.action_id" @click="choose()">
      <h3>{{ cardInfo.actor }}</h3>
    </div>
  </div>
</template>
