<script setup>
const keyStrengths = [
  {
    title: "Clean & Scalable Code",
    desc: "Menulis kode komponen yang modular, mudah dirawat, dan terstruktur dengan baik.",
    icon: "M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4",
  },
  {
    title: "Performance",
    desc: "Memastikan kecepatan rendering halaman optimal dan aset web terkompresi dengan baik.",
    icon: "M13 10V3L4 14h7v7l9-11h-7z",
  },
  {
    title: "Modern UI/UX Mindset",
    desc: "Komitmen untuk menghasilkan tampilan web yang presisi sesuai dengan desain asli (pixel-perfect).",
    icon: "M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zm0 0h12a2 2 0 002-2v-4a2 2 0 00-2-2h-2.343M11 7.343l1.657-1.657a2 2 0 012.828 0l2.829 2.829a2 2 0 010 2.828l-8.486 8.485M7 17h.01",
  },
  {
    title: "Collaborative & Adaptable",
    desc: " Komunikasi yang transparan dan kemampuan adaptasi di dalam tim lintas divisi.",
    icon: "M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z",
  },
];
</script>

<template>
  <section id="about" class="py-16 px-4 sm:px-6 relative">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center mb-10">
        <span
          class="text-xs font-bold uppercase tracking-widest text-emerald-400 bg-emerald-950/60 border border-emerald-800/40 px-3.5 py-1 rounded-full mb-3"
        >
          Get to Know Me
        </span>
        <h2
          class="text-3xl sm:text-4xl font-extrabold text-slate-100 tracking-tight"
        >
          About <span class="text-emerald-400">My Background</span>
        </h2>
        <p class="mt-4 text-slate-400 max-w-2xl text-sm sm:text-base">
          Mengenal latar belakang, pengalaman, dan pendekatan saya dalam
          membangun aplikasi web yang nyaman digunakan.
        </p>
      </div>

      <!-- Bio Card & Overview -->
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-stretch">
        <!-- Left: Personal Story & Highlight -->
        <div
          class="lg:col-span-5 bg-linear-to-b from-slate-900/80 to-slate-950/80 border border-slate-800/80 rounded-2xl p-6 sm:p-8 flex flex-col justify-between relative overflow-hidden"
        >
          <div
            class="absolute -right-10 -bottom-10 w-48 h-48 bg-emerald-500/10 rounded-full blur-2xl pointer-events-none"
          ></div>

          <div>
            <div
              class="w-16 h-16 rounded-2xl bg-emerald-500/10 border border-emerald-500/30 flex items-center justify-center text-emerald-400 mb-6"
            >
              <svg
                class="w-8 h-8"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"
                />
              </svg>
            </div>
            <h3 class="text-xl font-bold text-slate-100 mb-3">
              Building with Purpose
            </h3>
            <p class="text-slate-400 text-sm sm:text-base leading-relaxed mb-4">
              Saya memiliki ketertarikan kuat pada proses UI slicing dengan
              selalu memposisikan diri sebagai pengguna akhir untuk memastikan
              kenyamanan User Experience (UX). Melalui latar belakang akademik
              yang kuat dan pengalaman magang industri, saya terbiasa menulis
              kode yang terstruktur serta adaptif terhadap teknologi baru,
              termasuk pemanfaatan AI-assisted tools untuk efisiensi koding.
            </p>
          </div>

          <!-- Quick facts for HR -->
          <div
            class="mt-2 pt-6 border-t border-slate-800 flex flex-col gap-2.5 text-xs sm:text-sm"
          >
            <div class="flex items-center justify-between text-slate-300">
              <span class="text-slate-500">Location:</span>
              <span class="font-medium"
                >Indonesia (Open to Remote / Relocation)</span
              >
            </div>
            <div class="flex items-center justify-between text-slate-300">
              <span class="text-slate-500">Work Model:</span>
              <span class="font-medium text-emerald-400"
                >Full-time / Remote / WFO</span
              >
            </div>
            <div class="flex items-center justify-between text-slate-300">
              <span class="text-slate-500">Languages:</span>
              <span class="font-medium"
                >Indonesian (Native), English (Technical Fluency)</span
              >
            </div>
          </div>
        </div>

        <!-- Right: 4 Pillar Strengths -->
        <div class="lg:col-span-7 grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div
            v-for="item in keyStrengths"
            :key="item.title"
            class="bg-slate-900/50 hover:bg-slate-900/80 border border-slate-800/80 hover:border-emerald-500/40 rounded-2xl p-6 transition-all duration-200 group"
          >
            <div
              class="w-14 h-14 rounded-2xl bg-slate-800 group-hover:bg-emerald-500/20 text-emerald-400 flex items-center justify-center mb-4 transition-colors"
            >
              <svg
                class="w-6 h-6"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  :d="item.icon"
                />
              </svg>
            </div>
            <h4
              class="text-xl font-bold text-slate-100 group-hover:text-emerald-300 transition-colors mb-2"
            >
              {{ item.title }}
            </h4>
            <p class="text-slate-400 text-xs sm:text-base leading-relaxed">
              {{ item.desc }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
