<template>
  <section id="projects" class="bg-[var(--paper-deep)] px-[max(32px,calc((100vw-1176px)/2))] py-[120px] max-md:px-5 max-md:py-[92px]">
    <div class="mx-auto max-w-[1240px]">
      <div class="mb-14 flex items-end justify-between gap-8 max-md:flex-col max-md:items-start" data-aos="fade-up">
        <div>
          <p class="mb-[22px] font-['DM_Mono'] text-[11px] uppercase tracking-[.08em] text-[var(--blue)]">02 / Selected work</p>
          <h2 class="max-w-[720px] font-['Space_Grotesk'] text-[clamp(42px,5vw,72px)] font-bold leading-[.92] tracking-[-.045em]">
            Work shaped by clarity, craft, and intention.
          </h2>
        </div>

        <div class="font-['DM_Mono'] text-[10px] uppercase tracking-[.08em] text-[var(--muted)]">
          <span class="border-b border-[var(--ink)] pb-[5px]">Portfolio / 2025</span>
        </div>
      </div>

      <div class="space-y-10">
        <article
          v-for="(project, index) in projects"
          :key="project.title"
          class="group border-b border-[var(--ink)] pb-10"
          data-aos="fade-up"
          :data-aos-delay="index * 120"
        >
          <div class="grid gap-8 lg:grid-cols-[1.18fr_.82fr] lg:items-end">
            <div class="order-2 lg:order-1">
              <div class="mb-5 flex items-center justify-between gap-4 font-['DM_Mono'] text-[10px] uppercase tracking-[.08em] text-[var(--blue)]">
                <span>0{{ index + 1 }}</span>
                <span>{{ project.tags.join(' / ') }}</span>
              </div>

              <h3 class="mb-4 font-['Space_Grotesk'] text-[clamp(34px,4vw,58px)] font-bold leading-[.96] tracking-[-.045em]">
                {{ project.title }}
              </h3>

              <p class="max-w-[540px] text-[15px] leading-[1.8] text-[var(--muted)]">
                {{ project.description }}
              </p>

              <div v-if="project.link" class="mt-7">
                <a
                  :href="project.link"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="inline-flex items-center gap-2 border-b border-[var(--ink)] pb-[5px] text-[13px] font-semibold transition hover:text-[var(--blue)]"
                >
                  View project
                  <span aria-hidden="true">→</span>
                </a>
              </div>
            </div>

            <div class="order-1 overflow-hidden rounded-[22px] border border-[var(--ink)] bg-[var(--paper)] lg:order-2">
              <div class="aspect-[16/11] overflow-hidden bg-[var(--paper-deep)]">
                <img
                  :src="project.image"
                  :alt="project.title"
                  class="block h-full w-full object-cover saturate-[.75] transition duration-700 group-hover:scale-[1.04] group-hover:saturate-100"
                />
              </div>
            </div>
          </div>
        </article>
      </div>

      <div class="mt-16 grid gap-6 md:grid-cols-3">
        <article
          v-for="item in miniProjects"
          :key="item.title"
          class="group border border-[var(--ink)] bg-[var(--paper)] p-4 transition hover:-translate-y-1 hover:shadow-[0_18px_30px_rgba(23,23,23,0.06)]"
          data-aos="fade-up"
        >
          <div class="overflow-hidden border border-[var(--line)] bg-[var(--paper-deep)]">
            <div class="aspect-[4/3] w-full overflow-hidden">
              <img :src="item.image" :alt="item.title" class="block h-full w-full object-cover transition duration-500 group-hover:scale-[1.05]" />
            </div>
          </div>

          <div class="mt-5">
            <p class="mb-3 font-['DM_Mono'] text-[10px] uppercase tracking-[.08em] text-[var(--blue)]">{{ item.label }}</p>
            <h3 class="mb-2 font-['Space_Grotesk'] text-[clamp(22px,2.5vw,32px)] font-bold leading-none tracking-[-.04em]">
              {{ item.title }}
            </h3>
            <p class="text-[15px] leading-[1.7] text-[var(--muted)]">{{ item.text }}</p>
          </div>
        </article>
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
            'A showcase experience built for BPR Artomoro, combining frontend implementation with a polished visual system to present the brand and portfolio with clarity.',
          tags: ['React', 'Tailwind', 'UI Design', 'Laravel'],
          image: artomoImage,
        },
        {
          title: 'E-commerce Website',
          description:
            'An online shopping experience designed for smooth browsing, clear conversion paths, and a responsive storefront tailored for modern users.',
          tags: ['Figma', 'UI/UX', 'React', 'Firebase'],
          image: eCommerceGroup,
          link: 'https://kidi-anpas.vercel.app/'
        }
      ],
      miniProjects: [
        {
          label: '03 / Team Project',
          title: 'BPR Artomoro showcase',
          text: 'A clean digital presentation designed to highlight the team’s work, portfolio, and brand identity.',
          image: groupImage
        },
        {
          label: '04 / Team Build',
          title: 'Reycom site rebuild',
          text: 'A professional redesign approach using modern frontend tooling to refresh the company’s online presence.',
          image: reycomImage
        },
        {
          label: '05 / School Project',
          title: 'Salon website',
          text: 'A focused website concept built with a responsive interface and practical CRUD-oriented functionality.',
          image: salonImage
        }
      ]
    };
  }
};
</script>