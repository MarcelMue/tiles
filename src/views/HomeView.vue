<script setup lang="ts">
import TileItem from "../components/TileItem.vue";
import { Slider } from '@ckpack/vue-color';
</script>

<template>
  <div class="about">
    <table>
      <tr v-for="n in 4">
        <th v-for="n in 4">
          <TileItem :color1="typeof colors === 'object' ? colors.hex8 : colors" :color2="typeof colors2 === 'object' ? colors2.hex8 : colors2"/>
        </th>
      </tr>
    </table>
  </div>
  <div class="picker">
    <input type="radio" v-model="pickerChoice" value="0">color 1
    <input type="radio" v-model="pickerChoice" value="1">color 2
    <Slider v-if="pickerChoice == 0" v-model="colors"></Slider>
    <Slider v-if="pickerChoice == 1" v-model="colors2"></Slider>
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
      colors2: 'white',
    }
  },
}
</script>

<style>
.picker {
  margin: 20px;
}
</style>
