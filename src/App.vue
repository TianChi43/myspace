<template>
  <NavBar />
  <router-view :key="$route.fullPath" />
</template>

<script>
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",
  components: {
    NavBar,
  },
};
</script>

<style>
</style>
