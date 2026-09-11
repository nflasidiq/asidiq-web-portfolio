<script setup>
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<template>
  <footer class="py-12 px-4 sm:px-6 border-t border-slate-900 bg-slate-950 text-slate-500 text-xs">
    <div class="max-w-6xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-4">
      <div class="flex items-center gap-2">
        <span class="w-6 h-6 rounded-lg bg-emerald-500/20 text-emerald-400 font-bold flex items-center justify-center text-[10px]">
          AS
        </span>
        <span class="text-slate-400 font-medium">Ahmad Sidiq — Portfolio</span>
      </div>

      <p class="text-slate-500">
        © {{ new Date().getFullYear() }} Ahmad Sidiq. Crafted with Vue 3 & Tailwind CSS.
      </p>

      <button
        type="button"
        @click="scrollToTop"
        class="flex items-center gap-1.5 text-slate-400 hover:text-emerald-400 transition-colors cursor-pointer"
      >
        <span>Back to top</span>
        <svg class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" />
        </svg>
      </button>
    </div>
  </footer>
</template>
