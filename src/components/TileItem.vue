<script setup lang="ts">
import CardItem from "./CardItem.vue";
import QuadratPattern from "./patterns/Quadrat.vue"
import PantheonPattern from "./patterns/Pantheon.vue"
</script>

<template>
  <div id="flashcard" @click.exact="toggleCard()" @click.shift="toggleRotation()">
    <CardItem class="card" :color1="c1" :color2="c2" :comp="compChosen" :rot="cardRotation"/>
  </div>
</template>

<script lang="ts">
export default {
  name: "FlipCard",
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
  },
  data() {
    return {
      flipped: false,
      rotation: 0,
    }
  },
  computed: {
    c1() {
      return this.color1;
    },
    c2() {
      return this.color2;
    },
    cardRotation() {
      return String(this.rotation + "deg")
    },
    compChosen(){
      if (this.flipped) return PantheonPattern;
      else return QuadratPattern;
    }
  },
  methods: {
    toggleCard() {
      this.flipped = !this.flipped;
    },
    toggleRotation() {
      console.log(this.rotation)
      this.rotation = this.rotation + 90;
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