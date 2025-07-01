<script>
export default {
  name: "Navbar",
  data() {
    return {
      menuOpen: false,
      isSticky: false,
      links: [
        { name: "Home", href: "/" },
        { name: "About", href: "#about" },
        { name: "Skills", href: "#skills" },
        { name: "Services", href: "#services" },
        { name: "Contact", href: "#contact" },
      ],
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.isSticky = window.scrollY > 50;
    },
  },
};
</script>

<template>
  <nav
    :class="[
      'navbar navbar-expand-lg navbar-dark w-100 position-fixed top-0 start-0',
      isSticky ? 'shadow' : '',
    ]"
    :style="
      isSticky
        ? 'background: rgba(123, 47, 242, 0.15); backdrop-filter: blur(6px); transition: background 0.3s;'
        : 'background: transparent; transition: background 0.3s;'
    "
    style="z-index: 1050"
  >
    <div
      class="container d-flex align-items-center justify-content-between"
      style="min-height: 64px"
    >
      <!-- Logo -->
      <a
        class="navbar-brand fw-bold me-3"
        style="
          background: linear-gradient(45deg, rgb(228 201 255), #60a5fa);
          background-clip: text;
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
          color: transparent;
          font-size: 2rem;
          letter-spacing: 1px;
        "
        href="/"
        >Mahmudul Hasan</a
      >

      <!-- Toggle button for mobile -->
      <button
        class="navbar-toggler"
        type="button"
        @click="menuOpen = !menuOpen"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <!-- Navbar menu -->
      <div
        class="navbar-collapse justify-content-center"
        :class="{ show: menuOpen, collapse: !menuOpen }"
        id="navbarNav"
      >
        <ul class="navbar-nav">
          <li class="nav-item" v-for="link in links" :key="link.href">
            <a class="nav-link fw-semibold px-3" :href="link.href">{{
              link.name
            }}</a>
          </li>
        </ul>
      </div>

      <!-- CV Button -->
      <div class="d-none d-lg-block">
        <a
          href="/cv.pdf"
          target="_blank"
          class="btn btn-outline-light fw-semibold ms-3"
          style="border-radius: 30px; padding: 6px 20px"
        >
          Download CV
        </a>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  transition: background 0.3s;
}
</style>
