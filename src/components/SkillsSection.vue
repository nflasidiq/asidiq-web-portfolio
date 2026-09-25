<script setup>
const skillCategories = [
  {
    category: "Frontend Development",
    description:
      "Membangun antarmuka modern berbasis komponen dan menerapkan struktur HTML yang semantik.",
    skills: [
      { name: "Electron.js", level: "Basic" },
      { name: "HTML5 & CSS3", level: "Intermediate" },
      { name: "Tailwind CSS", level: "Intermediate" },
      { name: "Responsive Web Design", level: "Intermediate" },
      { name: "Vue.js", level: "Intermediate" },
      { name: "React.js", level: "Intermediate" },
      { name: "JavaScript (ES6+)", level: "Intermediate" },
      { name: "TypeScript", level: "Basic/Intermediate" },
    ],
  },
  {
    category: "Backend & APIs",
    description:
      "Memahami dasar komunikasi dengan server, integrasi REST API, dan pengelolaan data menggunakan database.",
    skills: [
      { name: "Node.js", level: "Basic/Intermediate" },
      { name: "RESTful API Integration", level: "Intermediate" },
      { name: "PostgreSQL / MySQL", level: "Intermediate" },
    ],
  },
  {
    category: "Tools & Workflow",
    description:
      "Penggunaan tools pengembangan, version control, dan alur kerja pengembangan aplikasi.",
    skills: [
      { name: "Postman", level: "Basic" },
      { name: "Vercel Deployment", level: "Basic" },
      { name: "Git & GitHub/GitLab", level: "Intermediate" },
      { name: "VS Code", level: "Intermediate" },
      { name: "Figma (Design to Code)", level: "Intermediate" },
    ],
  },
];
</script>

<template>
  <section id="skills" class="py-16 px-4 sm:px-6 relative bg-slate-950/40">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center mb-10">
        <span
          class="text-xs font-bold uppercase tracking-widest text-emerald-400 bg-emerald-950/60 border border-emerald-800/40 px-3.5 py-1 rounded-full mb-3"
        >
          Technical Expertise
        </span>
        <h2
          class="text-3xl sm:text-4xl font-extrabold text-slate-100 tracking-tight"
        >
          Skills & <span class="text-emerald-400">Tech Stack</span>
        </h2>
        <p class="mt-4 text-slate-400 max-w-2xl text-sm sm:text-base">
          Ringkasan teknologi, framework, dan tools yang saya gunakan dalam
          proses pengembangan aplikasi web.
        </p>
      </div>

      <!-- Categories Grid -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div
          v-for="cat in skillCategories"
          :key="cat.category"
          class="bg-slate-900/40 border border-slate-800/80 rounded-2xl p-6 sm:p-7 flex flex-col justify-between hover:border-emerald-500/40 transition-colors"
        >
          <div>
            <div class="flex items-center gap-2 mb-2">
              <span class="w-2.5 h-2.5 rounded-full bg-emerald-400"></span>
              <h3 class="text-lg font-bold text-slate-100">
                {{ cat.category }}
              </h3>
            </div>
            <p class="text-slate-400 text-xs sm:text-sm leading-relaxed mb-6">
              {{ cat.description }}
            </p>

            <div class="flex flex-wrap gap-2">
              <div
                v-for="skill in cat.skills"
                :key="skill.name"
                class="flex items-center bg-emerald-950/50 justify-between gap-2 w-full px-3 py-2 rounded-xl border border-slate-800/90 hover:border-emerald-500/30 transition-all text-xs"
              >
                <span class="font-medium text-emerald-400">{{ skill.name }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
