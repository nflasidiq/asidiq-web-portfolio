<script setup>
const stats = [
  { label: "D3 Teknik Informatika", value: "IPK 3.63" },
  { label: "Magang Profesional", value: "4 Bulan" },
  { label: "Built & Delivered", value: "3+ Projects" },
];

const techStack = [
  "Vue.js",
  "React.js",
  "Tailwind CSS",
  "Vite",
  "JavaScript",
  "Git",
];

// Path ke file CV
const cvPath = "/cv/CV-Frontend Developer-Naufal Asidiq.pdf";

const downloadAndOpenCV = () => {
  // 1. Buka CV di tab baru
  window.open(cvPath, "_blank");

  // 2. Otomatis trigger download
  const link = document.createElement("a");
  link.href = cvPath;
  link.download = "CV-Frontend Developer-Naufal Asidiq.pdf";
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
};
</script>

<template>
  <section
    id="hero"
    class="relative min-h-screen flex items-center justify-center pt-28 pb-16 px-4 sm:px-6 overflow-hidden"
  >
    <!-- Subtle Background Glow Effects -->
    <div
      class="absolute top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-emerald-500/15 rounded-full blur-3xl pointer-events-none"
    ></div>
    <div
      class="absolute top-1/3 right-10 w-72 h-72 bg-teal-500/10 rounded-full blur-3xl pointer-events-none"
    ></div>

    <div
      class="relative max-w-5xl mx-auto w-full flex flex-col items-center text-center"
    >
      <!-- Main Heading -->
      <h1
        class="text-4xl sm:text-6xl lg:text-4xl font-extrabold text-slate-100 tracking-tight leading-[1.15] max-w-4xl"
      >
        Membangun Antarmuka Web Modern yang
        <span
          class="bg-linear-to-r from-emerald-400 via-teal-300 to-emerald-500 bg-clip-text text-transparent"
        >
          Responsif, Efisien, dan Berorientasi pada Pengguna.
        </span>
      </h1>

      <!-- Bio / Subtitle targeted for Recruiters -->
      <p
        class="mt-6 text-base sm:text-lg text-slate-400 max-w-2xl leading-relaxed"
      >
        Halo, saya
        <span class="text-slate-200 font-semibold">Naufal Asidiq</span> —
        seorang Junior Front-End Developer lulusan Teknik Informatika Polban.
        Saya berspesialisasi dalam mentransformasikan desain Figma menjadi kode
        web yang interaktif, bersih, dan fungsional serta berpengalaman dalam
        menggunakan ekosistem Vue.js, React.js, dan Tailwind CSS.
      </p>

      <!-- Action Buttons -->
      <div class="mt-8 flex flex-wrap items-center justify-center gap-4">
        <a
          href="#projects"
          class="inline-flex items-center gap-2 bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-bold px-6 py-3.5 rounded-xl shadow-lg shadow-emerald-500/25 hover:shadow-emerald-500/40 hover:-translate-y-0.5 transition-all text-sm sm:text-base"
        >
          <span>View Featured Projects</span>
        </a>

        <button
          type="button"
          @click="downloadAndOpenCV"
          class="inline-flex items-center gap-2 bg-slate-900/80 hover:bg-slate-800 text-slate-200 hover:text-emerald-400 border border-slate-700/80 hover:border-emerald-500/50 font-semibold px-6 py-3.5 rounded-xl transition-all text-sm sm:text-base cursor-pointer"
        >
          <svg
            class="w-4 h-4 text-emerald-400"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"
            />
          </svg>
          <span>Download CV / Resume</span>
        </button>
      </div>

      <!-- Quick Metrics for HR -->
      <div
        class="mt-14 w-full grid grid-cols-3 gap-4 max-w-4xl pt-8 border-t border-slate-800/80"
      >
        <div
          v-for="stat in stats"
          :key="stat.label"
          class="flex flex-col items-center"
        >
          <span class="text-2xl sm:text-3xl font-extrabold text-emerald-400">{{
            stat.value
          }}</span>
          <span class="text-xs sm:text-sm text-slate-400 mt-1">{{
            stat.label
          }}</span>
        </div>
      </div>

      <!-- Tech Stack Ribbon -->
      <div
        class="mt-10 flex flex-wrap items-center justify-center gap-2 sm:gap-3"
      >
        <span
          class="text-xs uppercase tracking-wider text-slate-500 font-semibold mr-2"
          >Core Stack:</span
        >
        <span
          v-for="tech in techStack"
          :key="tech"
          class="px-3 py-1 text-xs font-medium text-slate-300 bg-slate-900/60 border border-slate-800 rounded-lg"
        >
          {{ tech }}
        </span>
      </div>
    </div>
  </section>
</template>
