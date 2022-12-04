<template>
  <div class="wrapper">
    <h1>Features Page Template...</h1>
    <nuxt-content :document="article" />
  </div>
</template>

<style lang="scss" scoped>
  @import "~static/style/grid.scss";
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
