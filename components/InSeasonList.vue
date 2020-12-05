<template>
  <div class="m-12 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-4">
    <div v-for="product in produce" v-bind:key="product.name"
         class="text-3xl">
      <a :href="'https://www.ecosia.org/search?q=' + product.name.replace('-', ' ').toLowerCase()" target="_blank">
      {{product.name.replace("-", " ")}}
      </a>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  name: "InSeasonList",
  props: ["produce"]
}
</script>

<style lang="postcss">
</style>

