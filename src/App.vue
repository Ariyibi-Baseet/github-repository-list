import HomeView from './views/HomeView.vue';

<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/> -->
  <HomeView />
</template>
<script>
import HomeView from "@/views/HomeView.vue";
export default {
  name: "App",
  components: {
    HomeView,
  },
};
</script>
<style>
/* global utilities */
:root {
  --github-clr: #4078c0;
  --github-clr2: #333;
}
</style>
