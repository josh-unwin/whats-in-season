<template>
  <div class="font-light text-5xl">
    Here’s what’s in season in the <span class="font-bold bg-blue-600 bg-opacity-25 rounded-lg px-3">{{location}}</span>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default {
  name: "LocationMessage",
  props: ["location"]
}
</script>

<style lang="postcss">
</style>