<template>
  <section
    id="home"
    class="relative mx-auto min-h-[780px] max-w-[1240px] overflow-visible bg-[radial-gradient(#c9c0b3_1px,transparent_1px)] bg-[length:18px_18px] bg-[position:calc(100%+10px)_135px] bg-no-repeat px-8 pb-[120px] pt-40 max-md:min-h-0 max-md:px-5 max-md:pb-[92px] max-md:pt-[130px]"
  >
    <div class="relative grid items-end gap-20 lg:grid-cols-[1.15fr_.85fr] max-md:gap-[54px]">
      <div data-aos="fade-up" data-aos-delay="100">
        <p class="mb-6 flex items-center gap-2.5 font-['DM_Mono'] text-xs font-medium uppercase tracking-[.08em] text-(--blue) before:h-px before:w-[34px] before:bg-(--blue)">
          Frontend developer / UI designer
        </p>
        <h1 class="mb-[34px] max-w-[780px] font-['Space_Grotesk'] text-[clamp(54px,8vw,112px)] font-bold leading-[.88] tracking-[-.045em]">
          Digital work with <em class="not-italic text-(--blue)">sharp edges.</em>
        </h1>
        <p class="max-w-[490px] text-lg leading-[1.6] text-(--muted)">
          I’m Jonathan, a frontend developer and UI/UX designer building clear, expressive digital experiences for ambitious teams.
        </p>
        <div class="mt-[34px] flex items-center gap-6">
          <a
            :href="`https://wa.me/${talk.whatsapp}`"
            class="inline-flex bg-(--blue) px-5 py-[15px] text-[13px] font-semibold  transition hover:-translate-y-0.5 hover:bg-[#0d38b0]"
          >
          <p class="text-white">
            Let’s talk
          </p>
            <v-icon name="bi-arrow-up-right" class="ml-2 text-white" />
          </a>
          <a href="#projects" class="border-b border-[var(--ink)] pb-[5px] text-[13px] font-semibold">
            See selected work ↓
          </a>
        </div>
      </div>

      <div data-aos="fade-left" data-aos-delay="150">
        <div class="relative">
          <div class="absolute left-[14px] top-[14px] z-0 h-full w-full border border-[var(--orange)]"></div>
          <img
            :src="heroImage"
            alt="Jonathan Iatsa Heroku Augta"
            class="relative z-[1] block h-[530px] w-full object-cover saturate-[.8] max-md:h-[min(110vw,500px)]"
          />
          <span class="absolute bottom-[-13px] left-[-14px] z-[2] bg-[var(--orange)] px-[14px] py-2.5 font-['DM_Mono'] text-[11px] tracking-[.08em] text-white">
            Available for new work 
          </span>
        </div>
      </div>
    </div>

    <div class="mt-[88px] flex gap-[52px] border-t border-[var(--line)] pt-5 max-md:mt-16 max-md:gap-6" data-aos="fade-up" data-aos-delay="250">
      <div>
        <div class="font-['Space_Grotesk'] text-[28px] font-bold">03</div>
        <div class="mt-1 text-[11px] text-[var(--muted)]">Years experience</div>
      </div>
      <div>
        <div class="font-['Space_Grotesk'] text-[28px] font-bold">10+</div>
        <div class="mt-1 text-[11px] text-(--muted)">Projects shipped</div>
      </div>
      <div>
        <div class="font-['Space_Grotesk'] text-[28px] font-bold">100%</div>
        <div class="mt-1 text-[11px] text-[var(--muted)]">Curiosity</div>
      </div>
    </div>
  </section>
</template>

<script>
import { OhVueIcon, addIcons } from 'oh-vue-icons';
import { BiArrowUpRight } from 'oh-vue-icons/icons/bi';
import heroImage from '../assets/ak.jpeg';

addIcons(BiArrowUpRight);

export default {
  components: {
    'v-icon': OhVueIcon
  },
  data() {
    return {
      heroImage,
      talk: {
        whatsapp: '6281227259583'
      }
    };
  }
};
</script>
