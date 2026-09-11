<script setup>
const stats = [
  { label: 'Years Experience', value: '2+' },
  { label: 'Completed Projects', value: '15+' },
  { label: 'Client Satisfaction', value: '100%' },
]

const techStack = ['Vue.js 3', 'Tailwind CSS', 'Vite', 'JavaScript (ES6+)', 'Node.js', 'Git']
</script>

<template>
  <section id="hero" class="relative min-h-screen flex items-center justify-center pt-28 pb-16 px-4 sm:px-6 overflow-hidden">
    <!-- Subtle Background Glow Effects -->
    <div class="absolute top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-emerald-500/15 rounded-full blur-3xl pointer-events-none"></div>
    <div class="absolute top-1/3 right-10 w-72 h-72 bg-teal-500/10 rounded-full blur-3xl pointer-events-none"></div>

    <div class="relative max-w-5xl mx-auto w-full flex flex-col items-center text-center">
      <!-- HR Status Badge -->
      <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-emerald-950/60 border border-emerald-500/30 text-emerald-400 text-xs sm:text-sm font-medium mb-6 shadow-sm shadow-emerald-500/10">
        <span class="relative flex h-2 w-2">
          <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
          <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
        </span>
        <span>Looking for New Opportunities & Projects</span>
      </div>

      <!-- Main Heading -->
      <h1 class="text-4xl sm:text-6xl lg:text-7xl font-extrabold text-slate-100 tracking-tight leading-[1.15] max-w-4xl">
        Crafting Modern Web Experiences with
        <span class="bg-linear-to-r from-emerald-400 via-teal-300 to-emerald-500 bg-clip-text text-transparent">
          Precision & Speed.
        </span>
      </h1>

      <!-- Bio / Subtitle targeted for Recruiters -->
      <p class="mt-6 text-base sm:text-lg text-slate-400 max-w-2xl leading-relaxed">
        Hi, I'm <span class="text-slate-200 font-semibold">Ahmad Sidiq</span> — a passionate Frontend & Web Developer specializing in Vue.js, Tailwind CSS, and performant user interfaces that drive business results.
      </p>

      <!-- Action Buttons -->
      <div class="mt-8 flex flex-wrap items-center justify-center gap-4">
        <a
          href="#projects"
          class="inline-flex items-center gap-2 bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-bold px-6 py-3.5 rounded-xl shadow-lg shadow-emerald-500/25 hover:shadow-emerald-500/40 hover:-translate-y-0.5 transition-all text-sm sm:text-base"
        >
          <span>View Featured Projects</span>
          <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
          </svg>
        </a>

        <a
          href="#contact"
          class="inline-flex items-center gap-2 bg-slate-900/80 hover:bg-slate-800 text-slate-200 hover:text-emerald-400 border border-slate-700/80 hover:border-emerald-500/50 font-semibold px-6 py-3.5 rounded-xl transition-all text-sm sm:text-base"
        >
          <svg class="w-4 h-4 text-emerald-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4" />
          </svg>
          <span>Download CV / Resume</span>
        </a>
      </div>

      <!-- Quick Metrics for HR -->
      <div class="mt-14 w-full grid grid-cols-3 gap-4 max-w-2xl pt-8 border-t border-slate-800/80">
        <div v-for="stat in stats" :key="stat.label" class="flex flex-col items-center">
          <span class="text-2xl sm:text-3xl font-extrabold text-emerald-400">{{ stat.value }}</span>
          <span class="text-xs sm:text-sm text-slate-400 mt-1">{{ stat.label }}</span>
        </div>
      </div>

      <!-- Tech Stack Ribbon -->
      <div class="mt-10 flex flex-wrap items-center justify-center gap-2 sm:gap-3">
        <span class="text-xs uppercase tracking-wider text-slate-500 font-semibold mr-2">Core Stack:</span>
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
