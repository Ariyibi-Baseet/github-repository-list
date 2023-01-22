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
  /* color */
  --github-clr: #4078c0;
  --github-clr2: #333;
  --gold: #ffd700;

  /* font family */
  --poppins: "Poppins", sans-serif;
  --playfair: "Playfair Display", serif;
}

* {
  font-family: var(--poppins);
}

/* text gradient and button gradient component */
.text-gradient-gold {
  background: hsla(42, 65%, 41%, 1);
  background: linear-gradient(
    135deg,
    hsla(42, 65%, 41%, 1) 0%,
    hsla(56, 87%, 75%, 1) 94%
  );
  background: -moz-linear-gradient(
    135deg,
    hsla(42, 65%, 41%, 1) 0%,
    hsla(56, 87%, 75%, 1) 94%
  );
  background: -webkit-linear-gradient(
    135deg,
    hsla(42, 65%, 41%, 1) 0%,
    hsla(56, 87%, 75%, 1) 94%
  );
  filter: progid: DXImageTransform.Microsoft.gradient( startColorstr="#AE8625", endColorstr="#F7EF8A", GradientType=1 );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.btn-gradient-gold {
  background: hsla(42, 65%, 41%, 1);
  background: linear-gradient(
    135deg,
    hsla(42, 65%, 41%, 1) 0%,
    hsla(56, 87%, 75%, 1) 94%
  );
  background: -moz-linear-gradient(
    135deg,
    hsla(42, 65%, 41%, 1) 0%,
    hsla(56, 87%, 75%, 1) 94%
  );
  background: -webkit-linear-gradient(
    135deg,
    hsla(42, 65%, 41%, 1) 0%,
    hsla(56, 87%, 75%, 1) 94%
  );
  filter: progid: DXImageTransform.Microsoft.gradient( startColorstr="#AE8625", endColorstr="#F7EF8A", GradientType=1 );
}
</style>
