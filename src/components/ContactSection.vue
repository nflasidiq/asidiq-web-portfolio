<script setup>
import { ref } from "vue";

const copied = ref(false);
const emailAddress = "naufalasidiq150@gmail.com";

const copyEmail = () => {
  navigator.clipboard.writeText(emailAddress);
  copied.value = true;
  setTimeout(() => {
    copied.value = false;
  }, 2000);
};

const socialLinks = [
  { name: "GitHub", href: "https://github.com/nflasidiq", icon: "github" },
  {
    name: "LinkedIn",
    href: "https://www.linkedin.com/in/naufal-asidiq-0876b2298/",
    icon: "linkedin",
  },
];
</script>

<template>
  <section id="contact" class="py-16 px-4 sm:px-6 relative bg-slate-950/60">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center mb-10">
        <span
          class="text-xs font-bold uppercase tracking-widest text-emerald-400 bg-emerald-950/60 border border-emerald-800/40 px-3.5 py-1 rounded-full mb-3"
        >
          Get in Touch
        </span>
        <h2
          class="text-3xl sm:text-4xl font-extrabold text-slate-100 tracking-tight"
        >
          Let's Work <span class="text-emerald-400">Together!</span>
        </h2>
        <p class="mt-4 text-slate-400 max-w-2xl text-sm sm:text-base">
          Terbuka untuk peluang kerja, proyek, maupun kolaborasi. Jangan ragu
          untuk menghubungi saya.
        </p>
      </div>

      <div class="max-w-xl mx-auto">
        <div
          class="bg-slate-900/50 border border-slate-800/80 rounded-2xl p-6 sm:p-6 text-center flex flex-col items-center"
        >
          <h3 class="text-xl font-bold text-slate-100 mb-2">Let's Connect!</h3>
          <p class="text-slate-400 text-sm mb-6 leading-relaxed max-w-lg">
            Saya sangat terbuka untuk peluang kerja dan kolaborasi yang sesuai
            dengan keahlian saya di bidang Front-End Development. Mari
            terhubung! Anda bisa menyalin alamat email saya secara instan.
          </p>

          <!-- Copy Email Box -->
          <div
            class="w-full max-w-md flex items-center justify-between p-3.5 rounded-xl bg-slate-950 border border-slate-800/90 mb-6 shadow-inner"
          >
            <div class="flex items-center gap-3 overflow-hidden">
              <svg
                class="w-5 h-5 text-emerald-400 shrink-0"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                />
              </svg>
              <span class="text-xs sm:text-sm text-slate-200 truncate">{{
                emailAddress
              }}</span>
            </div>
            <button
              type="button"
              @click="copyEmail"
              class="ml-2 text-xs font-semibold px-3.5 py-1.5 rounded-lg bg-emerald-500/10 hover:bg-emerald-500/20 text-emerald-400 border border-emerald-500/30 transition-all cursor-pointer shrink-0"
            >
              {{ copied ? "Copied! ✓" : "Copy" }}
            </button>
          </div>

          <!-- Social / Professional links -->
          <div
            class="w-full pt-6 border-t border-slate-800/80 flex flex-col items-center"
          >
            <span
              class="text-xs font-semibold text-slate-500 uppercase tracking-wider block mb-3"
            >
              Connect on Socials
            </span>
            <div class="flex flex-wrap justify-center gap-2">
              <a
                v-for="social in socialLinks"
                :key="social.name"
                :href="social.href"
                target="_blank"
                rel="noopener noreferrer"
                class="px-5 py-2 rounded-xl bg-slate-950 border border-slate-800 text-slate-300 hover:text-emerald-400 hover:border-emerald-500/40 text-xs font-medium transition-all"
              >
                {{ social.name }}
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
