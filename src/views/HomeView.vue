<script setup lang="ts">
import TileItem from "../components/TileItem.vue";
import { Slider } from '@ckpack/vue-color';
</script>

<template>
  <div class="about">
    <table>
      <tr v-for="n in 4">
        <th v-for="n in 4">
          <TileItem :flip="flip" :front="front" :back="back" :color1="typeof colors === 'object' ? colors['hex8'] : colors" :color2="typeof colors2 === 'object' ? colors2['hex8'] : colors2"/>
        </th>
      </tr>
    </table>
    <p class="picker">
      Flip
      <label class="switch">
        <input type="checkbox" @click="toggleCheckbox" >
        <div class="slider round"></div>
      </label>
      Rotate
    </p>
    <div class="picker">
      <input type="radio" v-model="pickerChoice" value="0">Color1
      <input type="radio" v-model="pickerChoice" value="1">Color2
      <Slider v-if="pickerChoice == 0" v-model="colors"></Slider>
      <Slider v-if="pickerChoice == 1" v-model="colors2"></Slider>
    </div>
    <div class="picker">
      <select v-model="front">
        <option disabled value="">Front Pattern</option>
        <option>janein</option>
        <option>pantheon</option>
        <option>quadrat</option>
      </select>
      <select v-model="back">
        <option disabled value="">Back Pattern</option>
        <option>janein</option>
        <option>pantheon</option>
        <option>quadrat</option>
      </select>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  components: {
    Slider,
  },
  data() {
    return {
      pickerChoice: 0,
      colors: 'white',
      colors2: 'black',
      flip: true,
      front: "quadrat",
      back: "pantheon",
    }
  },
  methods: {
    toggleCheckbox() {
      this.flip = !this.flip;
    },
  },
}
</script>

<style>
.picker {
  margin-top: 20px;
}
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

.switch input {
  display: none;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input:checked + .slider {
  background-color: #101010;
}

input:focus + .slider {
  box-shadow: 0 0 1px #101010;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
</style>
