<template>
  <section id="projects" class="bg-[var(--paper-deep)] px-[max(32px,calc((100vw-1176px)/2))] py-[120px] max-md:px-5 max-md:py-[92px]">
    <div>
      <div data-aos="fade-up">
        <p class="mb-[22px] font-['DM_Mono'] text-[11px] uppercase tracking-[.08em] text-[var(--blue)]">02 / Selected work</p>
        <h2 class="mb-7 max-w-[680px] font-['Space_Grotesk'] text-[clamp(42px,5vw,70px)] font-bold leading-[.95] tracking-[-.045em]">A few things I’ve helped bring to life.</h2>
      </div>

      <div class="border-t border-[var(--ink)]">
        <article
          v-for="(project, index) in projects"
          :key="project.title"
          class="group grid gap-[58px] border-b border-[var(--ink)] py-9 lg:grid-cols-[.9fr_1.1fr] max-md:gap-[42px]"
          data-aos="fade-up"
        >
          <div class="overflow-hidden">
            <img :src="project.image" :alt="project.title" class="block h-[280px] w-full object-cover saturate-[.75] transition duration-500 group-hover:scale-[1.03] group-hover:saturate-100 max-md:h-[240px]" />
          </div>

          <div class="self-center">
            <div class="mb-[30px] flex gap-7 font-['DM_Mono'] text-[10px] uppercase tracking-[.08em] text-[var(--blue)]">
              <span>0{{ index + 1 }}</span>
              <span>{{ project.tags.join(' / ') }}</span>
            </div>
            <h3 class="mb-[15px] font-['Space_Grotesk'] text-[clamp(30px,4vw,52px)] font-bold leading-none tracking-[-.045em]">{{ project.title }}</h3>
            <p class="mb-[26px] max-w-[560px] text-[15px] leading-[1.7] text-[var(--muted)]">{{ project.description }}</p>
            <a :href="project.link" target="_blank" rel="noopener noreferrer" class="border-b border-[var(--ink)] pb-[5px] text-[13px] font-semibold">
            </a>
            <div class="sr-only">
              <span v-for="tag in project.tags" :key="tag">{{ tag }}</span>
            </div>
          </div>
        </article>
      </div>

      <div class="mt-24 grid gap-[58px] border-t border-[var(--ink)] pt-[34px] lg:grid-cols-[.9fr_1.1fr] max-md:mt-[70px] max-md:gap-[42px]">
        <img :src="groupImage" alt="Portfolio showcase" class="h-[330px] w-full object-cover saturate-[.75]" />
        <div class="self-center">
          <p class="mb-[22px] font-['DM_Mono'] text-[11px] uppercase tracking-[.08em] text-[var(--blue)]">03 / Team Project of bpr artomoro</p>
          <h3 class="max-w-[530px] font-['Space_Grotesk'] text-[clamp(28px,3.5vw,48px)] font-bold leading-none tracking-[-.045em]">A polished showcase for GitHub, Figma, and other work.</h3>
          <p class="max-w-[520px] text-[15px] leading-[1.7] text-[var(--muted)]">
           last team project at artomoro, creating a polished showcase for GitHub, Figma, and other work. The project involved designing and implementing responsive interfaces that highlight the company’s portfolio and design process.
          </p>

        </div>
      </div>
      <div class="mt-24 grid gap-[58px] border-t border-[var(--ink)] pt-[34px] lg:grid-cols-[.9fr_1.1fr] max-md:mt-[70px] max-md:gap-[42px]">
        <img :src="salonImage" alt="Portfolio showcase" class="h-[330px] w-full object-cover saturate-[.75]" />
        <div class="self-center">
          <p class="mb-[22px] font-['DM_Mono'] text-[11px] uppercase tracking-[.08em] text-[var(--blue)]">04 / Solo Project At School</p>
          <h3 class="max-w-[530px] font-['Space_Grotesk'] text-[clamp(28px,3.5vw,48px)] font-bold leading-none tracking-[-.045em]">Salon website project for UKK </h3>
          <p class="max-w-[520px] text-[15px] leading-[1.7] text-[var(--muted)]">
           i make a solo project at school, creating a salon website project for UKK. The project involved designing and implementing responsive interfaces and using crud operations.
          </p>
          
        </div>
      </div>
      <div class="mt-24 grid gap-[58px] border-t border-[var(--ink)] pt-[34px] lg:grid-cols-[.9fr_1.1fr] max-md:mt-[70px] max-md:gap-[42px]">
        <img :src="reycomImage" alt="Portfolio showcase" class="h-[330px] w-full object-cover saturate-[.75]" />
        <div class="self-center">
          <p class="mb-[22px] font-['DM_Mono'] text-[11px] uppercase tracking-[.08em] text-(--blue)">05 / Team Project Reycom Data Solution</p>
          <h3 class="max-w-[530px] font-['Space_Grotesk'] text-[clamp(28px,3.5vw,48px)] font-bold leading-none tracking-[-.045em]">Rebuild Website from Reycom Data Solution </h3>
          <p class="max-w-[520px] text-[15px] leading-[1.7] text-[var(--muted)]">
          Team Project using next js and tailwind css, creating a rebuild website from Reycom Data Solution. The project involved designing and implementing responsive interfaces.
          </p>

        </div>
      </div>
    </div>
  </section>
</template>

<script>
import groupImage from '../assets/group.jpeg';
import artomoImage from '../assets/logoArtomoro.png';
import eCommerceGroup from '../assets/eCommerceGroup.jpeg';
import reycomImage from '../assets/reycom.jpeg';
import salonImage from '../assets/ukk.jpeg';

export default {
  data() {
    return {
      groupImage,
      artomoImage,
      eCommerceGroup,
      reycomImage,
      salonImage,
      projects: [
        {
          title: 'BPR Artomoro Project',
          description:
            'Work as a frontend developer and UI/UX designer for BPR Artomoro, creating a polished showcase for GitHub, Figma, and other work. The project involved designing and implementing responsive interfaces that highlight the company’s portfolio and design process.',
          tags: ['React', 'Tailwind', 'UI Design', 'Laravel'],
          image: artomoImage,
        },
        {
          title: 'E-commerce Website',
          description:
            'An e-commerce website offering a seamless online shopping experience with a user-friendly interface and responsive design for optimal performance across devices.',
          tags: ['Figma', 'UI/UX', 'React', 'Firebase'],
          image: eCommerceGroup,
          link: 'https://kidi-anpas.vercel.app/'
        }
      ]
    };
  }
};
</script>