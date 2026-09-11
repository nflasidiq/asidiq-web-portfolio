<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const navLinks = [
  { name: 'About', href: '#about' },
  { name: 'Skills', href: '#skills' },
  { name: 'Projects', href: '#projects' },
  { name: 'Contact', href: '#contact' },
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header
    :class="[
      'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
      isScrolled
        ? 'bg-slate-950/85 backdrop-blur-md border-b border-emerald-900/30 py-3 shadow-lg shadow-black/20'
        : 'bg-transparent py-5'
    ]"
  >
    <div class="max-w-6xl mx-auto px-4 sm:px-6 flex items-center justify-between">
      <!-- Logo / Brand -->
      <a href="#" class="flex items-center gap-2 group">
        <span class="w-9 h-9 rounded-xl bg-linear-to-tr from-emerald-600 to-emerald-400 flex items-center justify-center font-bold text-slate-950 text-base shadow-md shadow-emerald-500/20 group-hover:scale-105 transition-transform">
          AS
        </span>
        <span class="text-slate-100 font-semibold text-lg tracking-tight group-hover:text-emerald-400 transition-colors">
          asidiq<span class="text-emerald-400">.dev</span>
        </span>
      </a>

      <!-- Desktop Nav -->
      <nav class="hidden md:flex items-center gap-1 bg-slate-900/60 border border-slate-800/80 px-4 py-1.5 rounded-full backdrop-blur-sm">
        <a
          v-for="link in navLinks"
          :key="link.name"
          :href="link.href"
          class="px-4 py-1.5 text-sm font-medium text-slate-300 hover:text-emerald-400 hover:bg-emerald-500/10 rounded-full transition-all duration-200"
        >
          {{ link.name }}
        </a>
      </nav>

      <!-- CTA & Status -->
      <div class="hidden md:flex items-center gap-3">
        <div class="flex items-center gap-2 text-xs font-medium text-emerald-300 bg-emerald-950/50 border border-emerald-800/40 px-3 py-1.5 rounded-full">
          <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
          <span>Available for hire</span>
        </div>
        <a
          href="#contact"
          class="text-sm font-semibold bg-emerald-500 hover:bg-emerald-400 text-slate-950 px-4 py-2 rounded-xl transition-all shadow-md shadow-emerald-500/20 hover:shadow-emerald-500/40 hover:-translate-y-0.5"
        >
          Let's Talk
        </a>
      </div>

      <!-- Mobile Menu Button -->
      <button
        type="button"
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        class="md:hidden p-2 rounded-lg text-slate-400 hover:text-emerald-400 hover:bg-slate-900 border border-slate-800 transition-colors"
        aria-label="Toggle menu"
      >
        <svg v-if="!isMobileMenuOpen" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg v-else class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </div>

    <!-- Mobile Dropdown -->
    <div
      v-if="isMobileMenuOpen"
      class="md:hidden bg-slate-950/95 border-b border-slate-800 px-6 py-5 backdrop-blur-xl animate-in slide-in-from-top-4"
    >
      <div class="flex flex-col gap-3">
        <a
          v-for="link in navLinks"
          :key="link.name"
          :href="link.href"
          @click="isMobileMenuOpen = false"
          class="text-slate-300 hover:text-emerald-400 font-medium py-2 transition-colors"
        >
          {{ link.name }}
        </a>
        <div class="pt-3 border-t border-slate-800 flex flex-col gap-3">
          <div class="flex items-center gap-2 text-xs font-medium text-emerald-300 bg-emerald-950/40 border border-emerald-800/40 px-3 py-2 rounded-lg">
            <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
            <span>Available for hire</span>
          </div>
          <a
            href="#contact"
            @click="isMobileMenuOpen = false"
            class="text-center text-sm font-semibold bg-emerald-500 hover:bg-emerald-400 text-slate-950 py-2.5 rounded-xl transition-colors"
          >
            Let's Talk
          </a>
        </div>
      </div>
    </div>
  </header>
</template>
