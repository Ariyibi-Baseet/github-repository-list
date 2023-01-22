<template>
  <NavBar />
  <section id="header">
    <div class="container">
      <div class="row">
        <div class="col-md-6 mb-3">
          <div class="image-area mt-5">
            <i class="bi bi-github github-icon text-gradient-gold"></i>
            <h2 class="header-h2 mt-3 text-gradient-gold">
              Get My Github
              <br />
              Repositories Now!
            </h2>
            <p class="text-white mt-3 mb-3 fs-4">
              Let's help you keep track of your gihub repositories incase you forgot. We
              have over 10,000 users across the globe that are using our github finder
              solution platform. You can also be one of the today!
            </p>
          </div>
          <div class="button-divs mt-4">
            <div class="row">
              <div class="col-md-6">
                <a href="https://www.github.com"
                  ><button
                    class="btn btn-block w-100 mb-3 fs-5 text-white github-btn btn-gradient-gold"
                  >
                    Join Github
                  </button></a
                >
              </div>
              <div class="col-md-6">
                <a href="#"
                  ><button
                    class="btn btn-block w-100 mb-3 fs-5 text-white ariweb-btn btn-gradient-gold"
                  >
                    Join Ariweb Intern
                  </button></a
                >
              </div>
            </div>
          </div>
        </div>
        <div class="col-md-6 mb-3 content-wrapper">
          <div class="content-n-form">
            <p class="text-center text-white mt-5 fs-4">
              Please input your Github username here
            </p>
            <form class="mt-3 github-username-form">
              <input
                class="form-control form-control-lg mb-3 shadow-none"
                type="text"
                placeholder="Your github username"
                aria-label=".form-control-lg example"
              />
              <button
                class="btn btn-block btn-gradient-gold form-control form-control-lg fs-5 text-white"
              >
                Fetch My Repositories
              </button>
            </form>
          </div>
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
      handDrawnArrow: "/img/scribble-svgrepo-com.svg",
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
  /* background-image: url(../../public/img/bg-github.jpg); */
  background-image: linear-gradient(
      135deg,
      hsla(12, 100%, 1%, 1) 0%,
      rgba(128, 128, 128, 0.88) 84%
    ),
    url(../../public/img/bg-github.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  padding: 0 0 40px 0;
}
.github-icon {
  font-size: 4rem;
}
.header-h2 {
  font-size: 4rem;
  font-family: var(--playfair);
  position: relative;
  /* border: 1px solid white; */
}
.header-h2::after {
  content: url(../../public/img/scribble-svgrepo-com.svg);
  position: absolute;
  top: 0;
  right: 0;
}
/* remove arrow on smaller device */
@media screen and (max-width: 767px) {
  .header-h2::after {
    content: url(../../public/img/curved-downward-arrow-svgrepo-com.svg);
    position: absolute;
    top: 150px;
    right: 0;
  }
}

.content-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
}
/* .content-n-form {
  border: 2px solid white;
} */
.github-username-form {
  width: 100%;
  /* margin-right: auto; */
  float: right;
}
</style>
