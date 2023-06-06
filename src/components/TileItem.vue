<script setup lang="ts">
import CardItem from "./CardItem.vue";
import ToolingIcon from "./icons/IconTooling.vue";
import EcosystemIcon from "./icons/IconEcosystem.vue";
import CommunityIcon from "./icons/IconCommunity.vue";
import SupportIcon from "./icons/IconSupport.vue";
</script>

<template>
  <div id="flashcard" @click="toggleCard()">
    <CardItem class="card" :color="cardColor" :comp="compChosen"/>
  </div>
</template>

<script lang="ts">
export default {
  name: "FlipCard",
  data() {
    return {
      flipped: false,
    };
  },
  computed: {
    cardColor() {
      if (this.flipped) return "yellow";
      else return "blue";
    },
    compChosen(){
      if (this.flipped) return ToolingIcon;
      else return EcosystemIcon;
    }
  },
  methods: {
    toggleCard() {
      this.flipped = !this.flipped;
    },
  },
};
</script>

<style>
.card {
  display: block;
  width: 100px;
  height: 100px;
  /* padding: 80px 50px; */
  /*background-color: #51aae5;*/
  border-radius: 5px;
  margin: 2px;
  text-align: center;
  line-height: 27px;
  cursor: pointer;
  position: relative;
  color: #fff;
  font-weight: 600;
  font-size: 20px;
  will-change: transform;
}
</style>