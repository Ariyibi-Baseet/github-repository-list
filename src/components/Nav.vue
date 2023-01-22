<template>
  <nav
    class="navbar navbar-light bg-dark navbar-expand-lg bg-body-tertiary"
    data-bs-theme="dark"
  >
    <div class="container">
      <a class="navbar-brand fs-4 text-gradient-gold" href="#"> FindGithubRepo. </a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link" href="#">
              <button class="btn btn-block btn-gradient-gold fs-5">
                My Portfolio <i class="bi bi-folder2"></i>
              </button>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
.navbar-brand {
  font-family: var(--playfair);
}
</style>
