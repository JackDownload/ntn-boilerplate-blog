<template>
  <article v-if="categoryPost" class="main article">
    <h1 class="article-title">{{ categoryPost.title }}</h1>
    <p class="mt-4">{{ categoryPost.description }}</p>
  </article>
</template>
<script>
export default {
  async asyncData({ params, payload }) {
    if (payload) return { categoryPost: payload }
    else
      return {
        categoryPost: await require(`~/assets/content/categorys/${params.category}.json`),
      }
  },
}
</script>
