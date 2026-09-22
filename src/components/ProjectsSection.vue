<script setup>
const projects = [
  {
    id: 1,
    title: "Rebuild Web System - Telkom Test House",
    category: "Web Apps",
    desc: "Proyek nyata skala perusahaan saat magang di PT AKSII. Bertanggung jawab atas optimasi antarmuka, error handling, serta pembuatan fitur baru pelacakan data riwayat kalibrasi.",
    tags: ["Vue.js", "Tailwind CSS", "JavaScript", "UI Slicing"],
    impact: "100% Responsive Layout & Secured Session Timeout Control",
    featured: false,
  },
  {
    id: 2,
    title: "Dasbor Admin Ride-Hailing - Pemuda Express",
    category: "Web Apps",
    desc: "Sistem dasbor internal untuk otomatisasi alur kerja admin, manajemen data transaksi, dan pemantauan aktivitas mitra driver secara real-time (Tugas Akhir Kuliah).",
    tags: ["React.js", "Tailwind CSS", "REST API Integration"],
    impact: "Automated Workflow for Order Recapitulation",
    featured: false,
  },
  {
    id: 3,
    title: "To-List-an (Tulisan) - Desktop Productivity App",
    category: "Desktop Apps",
    desc: "Aplikasi produktivitas desktop berbasis Windows untuk menggabungkan fungsi manajemen daftar tugas (to-do list) dan catatan teks biasa secara simultan dalam satu file.",
    tags: ["Electron.js", "JavaScript", "AI-Assisted Development"],
    impact: "Solved Personal Daily Task Efficiency Constraint",
    featured: false,
  },
];
</script>

<template>
  <section id="projects" class="py-16 px-4 sm:px-6 relative">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center mb-10">
        <span
          class="text-xs font-bold uppercase tracking-widest text-emerald-400 bg-emerald-950/60 border border-emerald-800/40 px-3.5 py-1 rounded-full mb-3"
        >
          Featured Work
        </span>
        <h2
          class="text-3xl sm:text-4xl font-extrabold text-slate-100 tracking-tight"
        >
          Recent <span class="text-emerald-400">Projects</span>
        </h2>
        <p class="mt-4 text-slate-400 max-w-2xl text-sm sm:text-base">
          Kumpulan proyek yang saya kerjakan dengan fokus pada kualitas kode,
          pengalaman pengguna, dan kebutuhan nyata.
        </p>
      </div>

      <!-- Projects Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div
          v-for="project in projects"
          :key="project.id"
          class="bg-slate-900/40 hover:bg-slate-900/70 border border-slate-800/90 hover:border-emerald-500/50 rounded-2xl p-6 sm:p-7 flex flex-col justify-between transition-all duration-300 group hover:-translate-y-1 shadow-lg shadow-black/20"
        >
          <div>
            <!-- Card Top Bar -->
            <div class="flex items-center justify-between gap-2 mb-4">
              <span
                class="text-xs font-semibold px-2.5 py-1 rounded-md bg-slate-800 text-slate-300"
              >
                {{ project.category }}
              </span>
              <span
                v-if="project.featured"
                class="text-[11px] font-bold text-emerald-300 bg-emerald-950/60 border border-emerald-800/40 px-2.5 py-0.5 rounded-full flex items-center gap-1"
              >
                ★ Featured
              </span>
            </div>

            <h3
              class="text-xl font-bold text-slate-100 group-hover:text-emerald-400 transition-colors mb-2"
            >
              {{ project.title }}
            </h3>

            <p class="text-slate-400 text-sm leading-relaxed mb-4">
              {{ project.desc }}
            </p>

            <!-- Impact Metric for HR -->
            <div
              class="flex items-center gap-2 text-xs font-semibold text-emerald-400 bg-emerald-950/30 border border-emerald-900/30 px-3 py-1.5 rounded-lg mb-6"
            >
              <svg
                class="w-4 h-4 text-emerald-400 shrink-0"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"
                />
              </svg>
              <span>{{ project.impact }}</span>
            </div>

            <!-- Tags -->
            <div class="flex flex-wrap gap-1.5">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="text-xs font-medium px-2.5 py-1 rounded-lg bg-slate-950/80 border border-slate-800 text-slate-400"
              >
                {{ tag }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
