<template>
  <div class="w-3/4 mx-auto px-4">
    <h1 class="text-3xl font-semibold text-green-600">Super Blog Nuxtjs</h1>
    <article
      v-for="article of articles"
      :key="article._id"
      class="mt-7 text-gray-600"
    >
      <h2 class="text-5xl font-semibold mb-5">{{ article.titulo }}</h2>
      <p class="mb-5">{{ article.resumo }}</p>
      <p class="text-green-500 cursor-pointer" @click="$router.push(`blog/${article._id}`)">Ler mais</p>
    </article>
  </div>
</template>

<script>
export default {
  data() {
    return {
      articles: [],
    };
  },

  created() {
    this.getAllArticles();
  },

  methods: {
    async getAllArticles() {
      const { data } = await this.$axios.$get(
        "https://api.pistonapi.com/soper-blog/artigo"
      );

      this.articles = data
    },
  },
};
</script>

<style>
</style>
