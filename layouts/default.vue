<template>
  <div>
    <header-navbar />
    <div class="h-full my-16">
      <Nuxt />
    </div>
  </div>
</template>

<script>
import HeaderNavbar from "../components/HeaderNavbar.vue";
export default {
  components: { HeaderNavbar },
};
</script>

<style>
* {
  margin: 0;
  outline: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
