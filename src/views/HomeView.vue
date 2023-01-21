<template>
  <NavBar />
  <section id="header">
    <div class="container">
      <div class="row">
        <div class="col-md-6">
          <div class="image-area mt-5">
            <img :src="gitImg" alt="" class="git-image d-block" />
            <h2 class="header-h2 mt-3">
              Get My Github
              <br />
              Repositories Now!
            </h2>
            <p class="text-white mt-3">
              Let's help you keep track of your gihub repositories incase you forgot. We
              have over 10,000 users across the globe that are using our github finder
              solution platform. You can also be one of the today!
            </p>
          </div>
          <div class="button-divs">
            <div class="row">
              <div class="col-md-6">
                <a href="#"
                  ><button class="btn btn-info w-100 mb-3">Join Github</button></a
                >
              </div>
              <div class="col-md-6">
                <a href="#"
                  ><button class="btn btn-info w-100 mb-3">Join Ariweb Intern</button></a
                >
              </div>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <div class="content-n-form"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import NavBar from "@/components/Nav.vue";
export default {
  name: "HomeView",
  components: {
    NavBar,
  },
  data() {
    return {
      gitImg: "/img/github.svg",
    };
  },
  setup() {},
};
</script>

<style scoped>
#header {
  width: 100%;
  min-height: 100vh;
  background-color: var(--github-clr2);
  padding: 0 0 40px 0;
}
.git-image {
  width: 100px;
}
.header-h2 {
  font-size: 4rem;
}
</style>
