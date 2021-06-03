<template>
  <div class="w-screen h-14 bg-green-500 shadow-md flex items-center">
    <div class="pl-5" v-for="itemMenu of itemsMenu" :key="itemMenu.router">
      <p
        @click="$router.push(itemMenu.router)"
        class="text-white text-xl font-semibold cursor-pointer"
      >
        {{ itemMenu.label }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      itemsMenu: [],
    };
  },

  created() {
    this.itemsMenu = [
      {
        label: "Home",
        router: "/",
      },
      {
        label: "Blog",
        router: "/blog",
      },
    ];
  },
};
</script>