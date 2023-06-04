<template>
  <div id="flashcard" class="container" @click="toggleCard()">
    <transition name="flip" mode="out-in">
      <div v-bind:prop="flipped" class="card" v-on:click="">
          <component :is="cardSide" />
      </div>
    </transition>
  </div>
</template>

<script lang="ts">
import cardFront from "@/components/cardFront.vue";
import cardBack from "@/components/cardBack.vue";

export default {
  name: "FlipCard",
  data() {
    return {
      flipped: true,
    };
  },
  computed: {
    cardSide() {
      if (this.flipped) return cardFront;
      else return cardBack;
    },
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
  width: 150px;
  height: 175px;
  /* padding: 80px 50px; */
  background-color: #51aae5;
  border-radius: 7px;
  margin: 5px;
  text-align: center;
  line-height: 27px;
  cursor: pointer;
  position: relative;
  color: #fff;
  font-weight: 600;
  font-size: 20px;
  -webkit-box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  -moz-box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  will-change: transform;
}

.flip-enter-active {
  transition: all 0.4s ease;
}

.flip-leave-active {
  display: none;
}

.flip-enter,
.flip-leave {
  transform: rotateY(180deg);
  opacity: 0;
}
</style>

