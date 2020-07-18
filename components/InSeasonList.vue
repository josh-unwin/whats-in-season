<template>
  <div class="m-12 grid grid-cols-4 gap-4">
    <div v-for="product in produce" v-bind:key="product.name"
         class="text-3xl">
      {{product.name}}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      produce: []
    }
  },

  async fetch() {
    this.produce = await this.$content('produce/united-kingdom')
    .limit(30)
    .fetch()

    return {
      produce
    }
  }
}

</script>

<style lang="postcss">
</style>

