<template>
  <section id="about" class="mx-auto max-w-[1240px] px-8 py-[120px] max-md:px-5 max-md:py-[92px]">
    <div class="grid items-center gap-[110px] lg:grid-cols-2 max-md:gap-[42px]">
      <div data-aos="fade-right" data-aos-delay="100">
        <p class="mb-[22px] font-['DM_Mono'] text-[11px] uppercase tracking-[.08em] text-[var(--blue)]">01 / About</p>
        <h2 class="mb-7 max-w-155 font-['Space_Grotesk'] text-[clamp(42px,5vw,70px)] font-bold leading-[.95] tracking-[-.045em]">Design should make the complex feel obvious.</h2>
        <p class="max-w-140 text-[17px] leading-[1.7] text-(--muted)">
          I’m a frontend developer and UI/UX designer who loves turning ideas into beautiful interfaces that feel effortless to use.
          I focus on responsive design, smooth interactions, and thoughtful details that help brands stand out.
        </p>

        <div class="mt-10.5 border-t border-(--line)">
          <div v-for="item in highlights" :key="item.title" class="grid gap-5 border-b border-(--line) py-5 sm:grid-cols-[.7fr_1fr]">
            <h3 class="m-0 text-[17px] font-semibold">{{ item.title }}</h3>
            <p class="m-0 text-sm leading-[1.6] text-(--muted)">{{ item.text }}</p>
          </div>
        </div>

        <div class="mt-7 flex flex-wrap gap-2">
          <span v-for="skill in skills" :key="skill" class="border border-[var(--line)] px-2.5 py-2 font-['DM_Mono'] text-[11px] text-[var(--muted)]">{{ skill }}</span>
        </div>
      </div>
      <div class="relative" data-aos="fade-left" data-aos-delay="150">
        <img :src="profileImage" alt="Jonathan at work" class="block h-[620px] w-full object-cover saturate-[.75] max-md:h-[460px]" />
        <p class="absolute bottom-0 left-0 m-0 bg-[var(--ink)] px-[14px] py-[11px] font-['DM_Mono'] text-[10px] tracking-[.08em] text-white">Based in Indonesia / Working worldwide</p>
      </div>
    </div>
  </section>
</template>

<script>
import profileImage from '../assets/ak2.jpeg';

export default {
  data() {
    return {
      profileImage,
      highlights: [
        {
          title: 'Frontend Development',
          text: 'I create fast, responsive, and polished interfaces with modern JavaScript Framework and Tailwind workflows.'
        },
        {
          title: 'UI/UX Design',
          text: 'I focus on accessibility, clarity, and visual hierarchy to make products feel intuitive.'
        }
      ],
      skills: ['JavaScript', 'Tailwind CSS', 'UI Design', 'Responsive Web', 'Figma', 'Performance']
    };
  }
};
</script>