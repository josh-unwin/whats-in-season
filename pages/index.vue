<template>
  <div class="wrapper">
    <div class="header">
      <Logo />
    </div>
    <div class="container mx-auto">
      <LocationMessage location="United Kingdom" />
      <div class="flex justify-center items-center"></div>
      <InSeasonList :produce="produce" />
    </div>
  </div>
</template>

<script>
import Vue from "vue";
export default Vue.extend({
  data() {
    return {
      produce: [],
      countries: []
    }
  },
  async fetch() {
    this.produce = await this.$content('produce', {deep: true})
    .limit(20)
    .fetch()

    this.directories = this.produce.map(product => product.dir.replace("/produce/", ""));
    this.countries = [...new Set(this.directories)];

    return {
      produce,
      countries
    }
  }
  });
</script>

<style lang="postcss">
.wrapper {
  @apply min-h-screen;

  background: url("~assets/bg1.svg");
  background-size: cover;
}

.container {
  @apply w-full;
}

.header {
  @apply flex justify-end mx-10 py-4;
}

body {
  @apply text-charcoal;

  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}

.title {
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
