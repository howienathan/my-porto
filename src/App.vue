<template>
  <div class="min-h-screen overflow-hidden bg-[var(--paper)]">
    <Navbar />
    <Hero />
    <About />
    <Project />
    <Contact />
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
import Contact from './components/Contact.vue';

export default {
  components: {
    Navbar,
    Hero,
    About,
    Project,
    Contact
  },
  setup() {
    onMounted(() => {
      AOS.init({
        duration: 1200,
        once: true,
        offset: 60,
        easing: 'ease-out-quart',
        mirror: false,
        delay: 50,
      });
    });
  }
};
</script>