<template>
  <header class="fixed inset-x-0 top-0 z-30 bg-[var(--paper)] p-4 sm:px-6 sm:py-[18px]">
    <div class="mx-auto flex max-w-[1240px] items-center justify-between">
      <a href="#home" class="flex items-center gap-2.5 font-['Space_Grotesk'] text-lg font-bold">
        <span class="size-[11px] rounded-full bg-[var(--orange)]"></span>
        Jonathan Augta
      </a>

      <nav class="hidden items-center gap-8 md:flex">
        <a
          v-for="item in menu"
          :key="item.name"
          :href="item.href"
          class="text-[13px] font-semibold text-[var(--muted)] transition-colors hover:text-[var(--blue)]"
          @click="handleNavClick(item.href, $event)"
        >
          {{ item.name }}
        </a>
      </nav>

      <button
        type="button"
        class="hidden border-b border-[var(--ink)] pb-[3px] text-[13px] font-semibold md:block"
        @click="openEmail"
      >
        Start a project ↗
      </button>

      <button
        type="button"
        class="flex size-10 cursor-pointer items-center justify-center border border-[var(--line)] bg-transparent text-[var(--ink)] md:hidden"
        @click="isMenuOpen = !isMenuOpen"
        aria-label="Toggle menu"
      >
        <div class="relative h-4 w-4">
          <span aria-hidden="true">☰</span>
        </div>
      </button>
    </div>

    <div
      v-if="isMenuOpen"
      class="mx-auto mt-4 flex max-w-[1240px] flex-col gap-4 border border-[var(--line)] bg-[var(--paper)] p-5 md:hidden"
    >
      <div class="flex flex-col gap-3">
        <a
          v-for="item in menu"
          :key="item.name"
          :href="item.href"
          class="text-sm font-semibold"
          @click="handleNavClick(item.href, $event)"
        >
          {{ item.name }}
        </a>

        <button
          type="button"
          @click="openEmail"
          class="w-fit border-b border-[var(--ink)] pb-1 text-left text-[13px] font-semibold"
        >
          Let's Talk
        </button>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";

const menu = ref([
  { name: "Home", href: "#home" },
  { name: "About", href: "#about" },
  { name: "Project", href: "#projects" },
  { name: "Contact", href: "#contact" },
]);

const isMenuOpen = ref(false);

const handleNavClick = (href, event) => {
  isMenuOpen.value = false;

  if (href === "#contact") {
    event.preventDefault();
    openEmail();
    return;
  }

  if (href.startsWith("#")) {
    event.preventDefault();
    const section = document.querySelector(href);
    section?.scrollIntoView({
      behavior: "smooth",
      block: "start",
    });
  }
};

const openEmail = () => {
  window.open(
    "https://mail.google.com/mail/?view=cm&fs=1&to=jonathanaugta3@gmail.com",
    "_blank"
  );
};
</script>