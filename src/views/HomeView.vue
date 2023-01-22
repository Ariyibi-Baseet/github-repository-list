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
                v-model="githubUsername"
                aria-label=".form-control-lg example"
              />
              <button
                class="btn btn-block btn-gradient-gold form-control form-control-lg fs-5 text-white shadow-none"
                @click="githubUsernames = githubUsername"
                :disabled="!isValidInput"
                data-bs-toggle="modal"
                data-bs-target="#staticBackdrop"
              >
                Fetch My Repositories
              </button>

              <!-- <ul>
                <li v-for="repo in data" :key="repo.id">
                  {{ repo.name }}
                </li>
              </ul> -->

              <!-- List of repositories in modal -->
              <div
                class="modal fade"
                id="staticBackdrop"
                data-bs-backdrop="static"
                data-bs-keyboard="false"
                tabindex="-1"
                aria-labelledby="staticBackdropLabel"
                aria-hidden="true"
              >
                <div class="modal-dialog">
                  <div class="modal-content">
                    <div class="modal-header">
                      <h1 class="modal-title fs-5" id="staticBackdropLabel">
                        {{ githubUsernames }}
                      </h1>
                      <button
                        type="button"
                        class="btn-close"
                        data-bs-dismiss="modal"
                        aria-label="Close"
                      ></button>
                    </div>
                    <div class="modal-body">
                      <ul class="list-group">
                        <li class="list-group-item" v-for="repo in data" :key="repo.id">
                          {{ repo.name }}
                        </li>
                      </ul>
                    </div>
                    <div class="modal-footer">
                      <button
                        type="button"
                        class="btn btn-block btn-gradient-gold text-white"
                        data-bs-dismiss="modal"
                      >
                        Close
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import NavBar from "@/components/Nav.vue";
import { ref, watch, reactive, toRefs, computed } from "vue";
import { useToast } from "vue-toastification";
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
  setup() {
    const githubUsername = ref(null);
    const githubUsernames = ref(null);
    const isValidInput = computed(() => githubUsernames.value !== "");
    const state = reactive({ data: [] });
    const toast = useToast();

    watch(() => {
      if (githubUsernames.value)
        fetch(`https://api.github.com/users/${githubUsernames.value}/repos`)
          .then((response) => response.json())
          .then((data) => {
            state.data = data;
            console.log(data);
            if (data.message == "Not Found") {
              toast.error("This username is not registered on github");
            } else if (data.message == undefined) {
              toast.success("This user is registered on Github");
            }
            console.log("messages", data.message);
            githubUsername.value = "";
          });
    });

    return {
      githubUsername,
      githubUsernames,
      toast,
      ...toRefs(state),
      isValidInput,
    };
  },
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
