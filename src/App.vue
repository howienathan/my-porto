<template>
  <div class="min-h-screen overflow-hidden bg-[var(--paper)]">
    <Navbar />
    <Hero />
    <About />
    <Project />
  </div>
</template>
<script>
import AOS from 'aos';
import 'aos/dist/aos.css';
import { onMounted } from 'vue';
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import Project from './components/Project.vue';

export default {
  components: {
    Navbar,
    Hero,
    About,
    Project
  },
  setup() {
    onMounted(() => {
      AOS.init({
        duration: 800,
        once: false,
        offset: 100,
        easing: 'ease-in-out',
      });
    });
  }
};
</script>