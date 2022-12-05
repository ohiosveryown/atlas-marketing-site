<template>
  <div class="app">
    <h1>Feature Index</h1>

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
  </div>
</template>

<style lang="scss" scoped>
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
    methods: {
      fadeIn() {
        gsap.from(".app", {
          opacity: 0,
          duration: 1.2,
          delay: 0.15,
          stagger: 0.15,
          ease: Power4.easeOut,
        })
      },
    },
    mounted() {
      this.fadeIn()
    },
  }
</script>
