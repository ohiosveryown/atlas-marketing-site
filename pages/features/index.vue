<template>
  <ul class="width">
    <li class="card" v-for="feature of features" :key="feature.slug">
      <!-- <img class="icon" :src="`${feature.icon}`" /> -->
      <NuxtLink :to="'/features/' + feature.slug">
        <h3 class="inter">{{ feature.header }}</h3>
        <p class="dark">{{ feature.subheader }}</p>
      </NuxtLink>
      <!-- <img class="hero" :src="`${feature.hero}`" /> -->
    </li>
  </ul>
</template>

<style lang="scss" scoped>
  @import "~static/style/feature-detail.scss";

  li {
    margin: 2.4rem 0;
  }
</style>

<script>
  export default {
    data: () => ({
      features: null,
    }),
    async fetch() {
      this.features = await this.$content("features", { deep: true })
        .sortBy("title", "asc")
        .fetch()
    },

    methods: {},

    mounted() {},
  }
</script>
