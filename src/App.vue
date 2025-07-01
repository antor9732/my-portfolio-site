<script setup>
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import Skills from "./components/Skills.vue";
import Projects from "./components/Projects.vue";
import About from "./components/About.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <div class="bg-gradient min-vh-100 text-white">
    <Navbar />
    <main >
      <Hero />
      <Skills />
      <Projects />
      <About />
      <Contact />
    </main>
    <Footer />
  </div>
</template>
