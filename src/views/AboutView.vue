<script setup lang="ts">
import TileItem from "../components/TileItem.vue";
</script>

<template>
  <div class="about">
    <h1>I want this to be the tile page</h1>
    <TileItem />
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
