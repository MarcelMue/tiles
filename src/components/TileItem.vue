<script setup lang="ts">
import CardItem from "./CardItem.vue";
import BlockplayPattern from "./patterns/Blockplay.vue"
import QuadratPattern from "./patterns/Quadrat.vue"
import PantheonPattern from "./patterns/Pantheon.vue"
import JaneinPattern from "./patterns/Janein.vue"
</script>

<template>
  <div id="flashcard" @click.exact="toggleCard()">
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
        return "white"
      }
    },
    color2: {
      type: String,
      default(){
        return "white"
      }
    },
    front: {
      type: String,
      default(){
        return ""
      }
    },
    back: {
      type: String,
      default(){
        return ""
      }
    },
    flip: {
      type: Boolean,
      default(){
        return true
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
      if (this.flipped) return this.comp(this.back);
      else return this.comp(this.front);
    }
  },
  methods: {
    toggleCard() {
      if (this.flip){
        this.flipped = !this.flipped;
      } else {
        this.rotation = this.rotation + 90;
      }
    },
    comp(val: string){
      switch (val) {
        case "blockplay":
          return BlockplayPattern;
        case "janein":
          return JaneinPattern;
        case "pantheon":
          return PantheonPattern;
        case "quadrat":
          return QuadratPattern;
      }
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