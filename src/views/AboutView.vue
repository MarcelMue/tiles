<script setup lang="ts">
import TileItem from "../components/TileItem.vue";
</script>

<template>
  <div class="about">
    <table>
      <tr>
        <th><TileItem /></th>
        <th><TileItem /></th>
        <th><TileItem /></th>
      </tr>
      <tr>
        <td><TileItem /></td>
        <td><TileItem /></td>
        <td><TileItem /></td>
      </tr>
      <tr>
        <td><TileItem /></td>
        <td><TileItem /></td>
        <td><TileItem /></td>
      </tr>
    </table>
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
