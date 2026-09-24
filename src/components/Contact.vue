<template>
  <section id="contact" class="bg-[var(--paper)] px-[max(32px,calc((100vw-1176px)/2))] py-[120px] max-md:px-5 max-md:py-[92px]">
    <div class="mx-auto max-w-[1240px]">
      <div class="mb-12" data-aos="fade-up">
        <p class="mb-[22px] font-['DM_Mono'] text-[11px] uppercase tracking-[.08em] text-[var(--blue)]">03 / Contact</p>
        <h2 class="max-w-[740px] font-['Space_Grotesk'] text-[clamp(42px,5vw,72px)] font-bold leading-[.92] tracking-[-.045em]">
          Let’s build something sharp, clear, and memorable.
        </h2>
      </div>

      <div class="grid gap-8 lg:grid-cols-[1.1fr_.9fr]">
        <div class="rounded-[28px] border border-[var(--ink)] bg-[var(--paper-deep)] p-7 sm:p-8 lg:p-10" data-aos="fade-up">
          <div class="mb-6 flex items-center gap-5">
            <div class="overflow-hidden rounded-full border border-[var(--ink)] bg-[var(--paper)] p-1.5">
              <img :src="profileImage" alt="Jonathan Augta" class="block h-20 w-20 rounded-full object-cover" />
            </div>
            <div>
              <p class="font-['DM_Mono'] text-[10px] uppercase tracking-[.08em] text-[var(--blue)]">Available for work</p>
              <p class="mt-1 font-['Space_Grotesk'] text-[28px] font-bold tracking-[-.04em]">Jonathan Augta</p>
            </div>
          </div>

          <p class="mb-6 max-w-[500px] text-[15px] leading-[1.8] text-[var(--muted)]">
            I’m available for freelance work, product design, and frontend builds for teams that want clean digital experiences with real personality.
          </p>

          <div class="flex flex-wrap gap-4">
            <a
              :href="`mailto:${email}`"
              class="inline-flex items-center border-b border-[var(--ink)] pb-[5px] text-[13px] font-semibold transition duration-300 cursor-pointer hover:text-[var(--blue)] "
            >
              Email me
            </a>

            <button
              type="button"
              @click="openWhatsApp"
              class="inline-flex items-center gap-2 border border-[var(--ink)] bg-[var(--ink)] px-4 py-2.5 text-[13px] font-semibold text-[var(--paper)] transition duration-300 cursor-pointer hover:bg-[var(--blue)] hover:border-[var(--blue)]"
            >
              WhatsApp
            </button>
          </div>
        </div>

        <div class="rounded-[28px] border border-[var(--ink)] bg-[var(--paper)] p-7 sm:p-8 lg:p-10" data-aos="fade-up" data-aos-delay="100">
          <div class="space-y-6">
            <div class="border-b border-[var(--line)] pb-4">
              <p class="mb-2 font-['DM_Mono'] text-[10px] uppercase tracking-[.08em] text-[var(--blue)]">Email</p>
              <a :href="`mailto:${email}`" class="text-[18px] font-medium text-[var(--ink)] hover:text-[var(--blue)]">
                {{ email }}
              </a>
            </div>

            <div class="border-b border-[var(--line)] pb-4">
              <p class="mb-2 font-['DM_Mono'] text-[10px] uppercase tracking-[.08em] text-[var(--blue)]">WhatsApp</p>
              <button type="button" @click="openWhatsApp" class="text-left text-[18px] font-medium text-[var(--ink)] hover:text-[var(--blue)]">
                +62 812-2725-9583
              </button>
            </div>

            <div>
              <p class="mb-2 font-['DM_Mono'] text-[10px] uppercase tracking-[.08em] text-[var(--blue)]">Based in</p>
              <p class="text-[18px] font-medium text-[var(--ink)]">Indonesia / Available worldwide</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import profileImage from '../assets/ak.jpeg';

export default {
  data() {
    return {
      profileImage,
      email: 'jonathanaugta3@gmail.com',
      whatsapp: '6281227259583',
      message: 'Hi Jonathan, I would like to discuss a project with you.'
    };
  },
  methods: {
    openWhatsApp() {
      const url = `https://wa.me/${this.whatsapp}?text=${encodeURIComponent(this.message)}`;
      window.open(url, '_blank', 'noopener,noreferrer');
    }
  }
};
</script>
