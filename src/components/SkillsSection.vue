<script setup>
const skillCategories = [
  {
    category: 'Frontend Development',
    description: 'Modern component-driven interfaces, reactive state management, and semantic markup.',
    skills: [
      { name: 'Vue.js (Vue 3 / Composition API)', level: 'Advanced' },
      { name: 'Tailwind CSS (v3 & v4)', level: 'Advanced' },
      { name: 'JavaScript (ES6+)', level: 'Advanced' },
      { name: 'HTML5 & CSS3', level: 'Advanced' },
      { name: 'TypeScript', level: 'Intermediate' },
      { name: 'Vite & Build Tools', level: 'Advanced' },
      { name: 'Responsive Web Design', level: 'Advanced' },
    ],
  },
  {
    category: 'Backend & APIs',
    description: 'Server communication, RESTful APIs integration, and database fundamentals.',
    skills: [
      { name: 'Node.js & Express', level: 'Intermediate' },
      { name: 'RESTful API Integration', level: 'Advanced' },
      { name: 'PostgreSQL / MySQL', level: 'Intermediate' },
      { name: 'JSON & Async Workflows', level: 'Advanced' },
    ],
  },
  {
    category: 'Tools, DevOps & Workflow',
    description: 'Version control, development tooling, and industry standard practices.',
    skills: [
      { name: 'Git & GitHub', level: 'Advanced' },
      { name: 'VS Code', level: 'Advanced' },
      { name: 'Postman', level: 'Intermediate' },
      { name: 'Figma (Design to Code)', level: 'Intermediate' },
      { name: 'NPM / Package Management', level: 'Advanced' },
    ],
  },
]
</script>

<template>
  <section id="skills" class="py-16 px-4 sm:px-6 relative bg-slate-950/40">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center mb-16">
        <span class="text-xs font-bold uppercase tracking-widest text-emerald-400 bg-emerald-950/60 border border-emerald-800/40 px-3.5 py-1 rounded-full mb-3">
          Technical Expertise
        </span>
        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-100 tracking-tight">
          Skills & <span class="text-emerald-400">Tech Stack</span>
        </h2>
        <p class="mt-4 text-slate-400 max-w-2xl text-sm sm:text-base">
          A categorized overview of technologies, frameworks, and developer tools I utilize daily to build scalable web software.
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
              <h3 class="text-lg font-bold text-slate-100">{{ cat.category }}</h3>
            </div>
            <p class="text-slate-400 text-xs sm:text-sm leading-relaxed mb-6">
              {{ cat.description }}
            </p>

            <div class="flex flex-wrap gap-2">
              <div
                v-for="skill in cat.skills"
                :key="skill.name"
                class="flex items-center justify-between gap-2 w-full px-3 py-2 rounded-xl bg-slate-950/70 border border-slate-800/90 hover:border-emerald-500/30 transition-all text-xs"
              >
                <span class="font-medium text-slate-200">{{ skill.name }}</span>
                <span class="text-[11px] font-semibold text-emerald-400 bg-emerald-950/50 border border-emerald-900/40 px-2 py-0.5 rounded-md">
                  {{ skill.level }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
