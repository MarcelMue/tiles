<template>
  <div id="flashcard" class="container" @click="toggleCard()">
    <transition name="flip" mode="out-in">
          <component :is="cardSide" class="card"/>
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
      flipped: false,
    };
  },
  computed: {
    cardSide() {
      if (this.flipped) return cardFront;
      else return cardBack;
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


.flip-enter-active, .flip-leave-active {
  transition: all 0.2s ease;
}

.flip-enter-from,
.flip-leave-to {
  transform: rotateY(180deg);
  opacity: 0;
}
</style>

