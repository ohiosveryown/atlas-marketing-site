<template>
  <div class="app width">
    <img class="icon" :src="`${article.icon}`" />
    <h1>{{ article.name }}</h1>
    <figure class="hero">
      <img :src="`${article.hero}`" />
    </figure>
    <nuxt-content :document="article" />
  </div>
</template>

<style lang="scss" scoped>
  @import "~static/style/feature-detail.scss";
</style>

<script>
  export default {
    async asyncData({ $content, params }) {
      const article = await $content("features", params.slug).fetch()

      return {
        article,
      }
    },

    methods: {},

    mounted() {},
  }
</script>
