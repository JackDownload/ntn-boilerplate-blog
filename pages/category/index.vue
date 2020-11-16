<template>
  <main v-if="categoryPosts" class="main">
    <h1 class="title text-left">Projects</h1>
    <ul v-for="(categoryPost, index) in categoryPosts" :key="index" class="articles">
      <nuxt-link class="article article--clickable" :to="`category/${categoryPost.slug}`">
        <h3 class="article-title">{{ categoryPost.title }}</h3>
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
}
</script>
