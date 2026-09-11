<script setup>
import { ref } from 'vue'

const activeFilter = ref('All')

const filters = ['All', 'Web Apps', 'Frontend UI', 'Fullstack']

const projects = [
  {
    id: 1,
    title: 'Enterprise Analytics Dashboard',
    category: 'Web Apps',
    desc: 'Interactive enterprise KPI monitoring dashboard with customizable widgets, real-time charts, and data filtering capabilities.',
    tags: ['Vue.js 3', 'Tailwind CSS', 'Chart.js', 'Vite'],
    impact: 'Improved reporting efficiency by 40%',
    liveUrl: 'https://example.com',
    githubUrl: 'https://github.com',
    featured: true,
  },
  {
    id: 2,
    title: 'E-Commerce Marketplace Platform',
    category: 'Fullstack',
    desc: 'High-conversion online shopping experience featuring product catalog filtering, cart management, and seamless checkout flow.',
    tags: ['Vue.js', 'Node.js', 'Tailwind CSS', 'REST API'],
    impact: 'Sub-second page load times with 99.8% uptime',
    liveUrl: 'https://example.com',
    githubUrl: 'https://github.com',
    featured: true,
  },
  {
    id: 3,
    title: 'SaaS Task Management Workspace',
    category: 'Web Apps',
    desc: 'Kanban-style productivity app with drag-and-drop task boards, role-based access control, and team activity timeline.',
    tags: ['Vue 3', 'Composition API', 'Tailwind', 'Pinia'],
    impact: 'Adopted by 500+ active beta testers',
    liveUrl: 'https://example.com',
    githubUrl: 'https://github.com',
    featured: false,
  },
  {
    id: 4,
    title: 'Modern Brand Landing Page & UI Kit',
    category: 'Frontend UI',
    desc: 'Pixel-perfect, ultra-responsive marketing website with smooth micro-interactions, dark mode toggle, and accessible components.',
    tags: ['Vue 3', 'Tailwind CSS v4', 'Vite', 'Accessible UI'],
    impact: '100% Lighthouse Performance & SEO Score',
    liveUrl: 'https://example.com',
    githubUrl: 'https://github.com',
    featured: false,
  },
]

const filteredProjects = () => {
  if (activeFilter.value === 'All') return projects
  return projects.filter((p) => p.category === activeFilter.value)
}
</script>

<template>
  <section id="projects" class="py-24 px-4 sm:px-6 relative">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center mb-12">
        <span class="text-xs font-bold uppercase tracking-widest text-emerald-400 bg-emerald-950/60 border border-emerald-800/40 px-3.5 py-1 rounded-full mb-3">
          Featured Work
        </span>
        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-100 tracking-tight">
          Recent <span class="text-emerald-400">Projects</span>
        </h2>
        <p class="mt-4 text-slate-400 max-w-2xl text-sm sm:text-base">
          A showcase of web applications built with a focus on code quality, performance, and real-world business impact.
        </p>
      </div>

      <!-- Filter Buttons -->
      <div class="flex flex-wrap items-center justify-center gap-2 mb-12">
        <button
          v-for="filter in filters"
          :key="filter"
          @click="activeFilter = filter"
          :class="[
            'px-4 py-2 text-xs sm:text-sm font-semibold rounded-xl transition-all duration-200 cursor-pointer',
            activeFilter === filter
              ? 'bg-emerald-500 text-slate-950 shadow-md shadow-emerald-500/20'
              : 'bg-slate-900/60 text-slate-400 hover:text-slate-200 border border-slate-800 hover:border-slate-700'
          ]"
        >
          {{ filter }}
        </button>
      </div>

      <!-- Projects Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div
          v-for="project in filteredProjects()"
          :key="project.id"
          class="bg-slate-900/40 hover:bg-slate-900/70 border border-slate-800/90 hover:border-emerald-500/50 rounded-2xl p-6 sm:p-7 flex flex-col justify-between transition-all duration-300 group hover:-translate-y-1 shadow-lg shadow-black/20"
        >
          <div>
            <!-- Card Top Bar -->
            <div class="flex items-center justify-between gap-2 mb-4">
              <span class="text-xs font-semibold px-2.5 py-1 rounded-md bg-slate-800 text-slate-300">
                {{ project.category }}
              </span>
              <span v-if="project.featured" class="text-[11px] font-bold text-emerald-300 bg-emerald-950/60 border border-emerald-800/40 px-2.5 py-0.5 rounded-full flex items-center gap-1">
                ★ Featured
              </span>
            </div>

            <h3 class="text-xl font-bold text-slate-100 group-hover:text-emerald-400 transition-colors mb-2">
              {{ project.title }}
            </h3>

            <p class="text-slate-400 text-sm leading-relaxed mb-4">
              {{ project.desc }}
            </p>

            <!-- Impact Metric for HR -->
            <div class="flex items-center gap-2 text-xs font-semibold text-emerald-400 bg-emerald-950/30 border border-emerald-900/30 px-3 py-1.5 rounded-lg mb-6">
              <svg class="w-4 h-4 text-emerald-400 shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />
              </svg>
              <span>{{ project.impact }}</span>
            </div>

            <!-- Tags -->
            <div class="flex flex-wrap gap-1.5 mb-6">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="text-xs font-medium px-2.5 py-1 rounded-lg bg-slate-950/80 border border-slate-800 text-slate-400"
              >
                {{ tag }}
              </span>
            </div>
          </div>

          <!-- Action Links -->
          <div class="pt-4 border-t border-slate-800/80 flex items-center justify-between gap-4">
            <a
              :href="project.githubUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center gap-1.5 text-xs font-semibold text-slate-400 hover:text-slate-100 transition-colors"
            >
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.53 1.032 1.53 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z" />
              </svg>
              <span>Source Code</span>
            </a>

            <a
              :href="project.liveUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center gap-1.5 text-xs font-semibold text-emerald-400 hover:text-emerald-300 transition-colors"
            >
              <span>Live Preview</span>
              <svg class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
