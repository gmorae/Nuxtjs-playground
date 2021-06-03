<template>
  <div class="w-3/4 mx-auto px-4">
    <article class="mt-7 text-gray-600">
      <h1 class="text-3xl font-semibold">
        {{ article.titulo }}
      </h1>
      <p class="my-3">{{ article.resumo }}</p>
      <p class="text-green-500 cursor-pointer" @click="$router.push(`/blog`)">
        Voltar
      </p>
    </article>
  </div>
</template>

<script>
export default {
  data() {
    return {
      article: [],
    };
  },

  created() {
    this.getArticle();
  },

  methods: {
    async getArticle() {
      this.article = await this.$axios.$get(
        `https://api.pistonapi.com/soper-blog/artigo/${this.$route.params.id}`
      );
    },
  },
};
</script>

<style>
</style>
