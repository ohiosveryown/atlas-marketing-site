<template>
  <div>
    <h1>Changlog...</h1>
    <ul>
      <li v-for="article of changelog" :key="article.slug">
        <NuxtLink :to="'/changelog/' + article.slug">
          <span class="title">{{ article.title }}</span>
        </NuxtLink>
      </li>
    </ul>

    <h1>features...</h1>
    <ul>
      <li v-for="feature of features" :key="feature.slug">
        <NuxtLink :to="'/features/' + feature.slug">
          <span class="title">{{ feature.title }}</span>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data: () => ({
      features: null,
      changelog: null,
    }),
    async fetch() {
      this.features = await this.$content("features", { deep: true })
        .sortBy("createdAt", "asc")
        .fetch()

      this.changelog = await this.$content("changelog", { deep: true })
        .sortBy("createdAt", "asc")
        .fetch()
    },
  }
</script>