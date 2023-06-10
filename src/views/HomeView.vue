<script setup lang="ts">
import TileItem from "../components/TileItem.vue";
import { Slider } from '@ckpack/vue-color';
</script>

<template>
  <div class="about">
    <p>
      Click to flip, Ctrl + click to rotate.
    </p>
    <table>
      <tr v-for="n in 4">
        <th v-for="n in 4">
          <TileItem :color1="typeof colors === 'object' ? colors['hex8'] : colors" :color2="typeof colors2 === 'object' ? colors2['hex8'] : colors2"/>
        </th>
      </tr>
    </table>
    <div class="picker">
      <input type="radio" v-model="pickerChoice" value="0">Color1
      <input type="radio" v-model="pickerChoice" value="1">Color2
      <Slider v-if="pickerChoice == 0" v-model="colors"></Slider>
      <Slider v-if="pickerChoice == 1" v-model="colors2"></Slider>
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
    }
  },
}
</script>

<style>
.picker {
  margin-top: 20px;
}
</style>
