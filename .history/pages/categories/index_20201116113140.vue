<template>
  <main v-if="categoryPost" class="main">
    <h1 class="title text-left">CategoryPost</h1>
    <ul v-for="(categoryPost, index) in categoryPost" :key="index" class="articles">
      <nuxt-link :to="`category/${categoryPost.slug}`" class="article article--clickable">
        <div class="flex justify-between align-baseline"></div>
        <div class="mt-4 mb-2">
          <p class="inline">{{ categoryPost.description }}</p>
        </div>
      </nuxt-link>
    </ul>
  </main>
</template>
<script>
export default {
  computed: {
    categoryPosts() {
      return this.$store.state.categoryPosts
    },
  },
  methods: {
    formatDate(dateString) {
      const date = new Date(dateString)
      return date.toLocaleDateString(process.env.lang) || ''
    },
  },
}
</script>
