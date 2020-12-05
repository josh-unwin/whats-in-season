<template>
  <div class="font-light text-5xl">
    Here’s what’s in season in the 
    <span class="font-bold bg-blue-600 hover:bg-blue-500 hover:bg-opacity-25 bg-opacity-25 rounded-lg px-3 pb-1 cursor-pointer">
      {{location}}<fa class="ml-1 text-4xl pb-2" :icon="['fas', 'caret-down']" />
    </span> right now
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