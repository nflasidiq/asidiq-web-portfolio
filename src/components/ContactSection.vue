<script setup>
import { ref } from 'vue'

const copied = ref(false)
const emailAddress = 'ahmadsidiq.dev@gmail.com'

const formSubmitted = ref(false)
const formData = ref({
  name: '',
  email: '',
  message: '',
})

const copyEmail = () => {
  navigator.clipboard.writeText(emailAddress)
  copied.value = true
  setTimeout(() => {
    copied.value = false
  }, 2000)
}

const handleSubmit = () => {
  formSubmitted.value = true
  setTimeout(() => {
    formData.value = { name: '', email: '', message: '' }
    formSubmitted.value = false
  }, 4000)
}

const socialLinks = [
  { name: 'GitHub', href: 'https://github.com', icon: 'github' },
  { name: 'LinkedIn', href: 'https://linkedin.com', icon: 'linkedin' },
  { name: 'Twitter / X', href: 'https://x.com', icon: 'twitter' },
]
</script>

<template>
  <section id="contact" class="py-16 px-4 sm:px-6 relative bg-slate-950/60">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center mb-16">
        <span class="text-xs font-bold uppercase tracking-widest text-emerald-400 bg-emerald-950/60 border border-emerald-800/40 px-3.5 py-1 rounded-full mb-3">
          Get in Touch
        </span>
        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-100 tracking-tight">
          Let's Work <span class="text-emerald-400">Together</span>
        </h2>
        <p class="mt-4 text-slate-400 max-w-2xl text-sm sm:text-base">
          Have an exciting project, full-time role, or consulting inquiry? My inbox is always open.
        </p>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">
        <!-- Left: Contact Details & Fast Channels -->
        <div class="lg:col-span-5 flex flex-col gap-6">
          <div class="bg-slate-900/50 border border-slate-800/80 rounded-2xl p-6 sm:p-7">
            <h3 class="text-lg font-bold text-slate-100 mb-2">Direct Contact</h3>
            <p class="text-slate-400 text-sm mb-6 leading-relaxed">
              Feel free to reach out directly via email or connect on professional networks.
            </p>

            <!-- Copy Email Box -->
            <div class="flex items-center justify-between p-3.5 rounded-xl bg-slate-950 border border-slate-800/90 mb-4">
              <div class="flex items-center gap-3 overflow-hidden">
                <svg class="w-5 h-5 text-emerald-400 shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                </svg>
                <span class="text-xs sm:text-sm text-slate-200 truncate">{{ emailAddress }}</span>
              </div>
              <button
                type="button"
                @click="copyEmail"
                class="ml-2 text-xs font-semibold px-3 py-1.5 rounded-lg bg-emerald-500/10 hover:bg-emerald-500/20 text-emerald-400 border border-emerald-500/30 transition-all cursor-pointer"
              >
                {{ copied ? 'Copied! ✓' : 'Copy' }}
              </button>
            </div>

            <!-- Social / Professional links -->
            <div class="pt-4 border-t border-slate-800/80">
              <span class="text-xs font-semibold text-slate-500 uppercase tracking-wider block mb-3">
                Connect on Socials
              </span>
              <div class="flex flex-wrap gap-2.5">
                <a
                  v-for="social in socialLinks"
                  :key="social.name"
                  :href="social.href"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="px-3.5 py-2 rounded-xl bg-slate-950 border border-slate-800 text-slate-300 hover:text-emerald-400 hover:border-emerald-500/40 text-xs font-medium transition-all"
                >
                  {{ social.name }}
                </a>
              </div>
            </div>
          </div>

          <!-- Availability Card -->
          <div class="bg-linear-to-br from-emerald-950/40 to-slate-900/60 border border-emerald-900/40 rounded-2xl p-6">
            <div class="flex items-center gap-2 mb-2 text-emerald-400 text-xs font-bold uppercase tracking-wider">
              <span class="w-2 h-2 rounded-full bg-emerald-400"></span>
              Current Status
            </div>
            <p class="text-slate-200 font-semibold text-sm">
              Actively interviewing for Frontend & Fullstack positions.
            </p>
            <p class="text-slate-400 text-xs mt-1">
              Response time: typically within 24 hours.
            </p>
          </div>
        </div>

        <!-- Right: Inquiry Form -->
        <div class="lg:col-span-7 bg-slate-900/50 border border-slate-800/80 rounded-2xl p-6 sm:p-8">
          <h3 class="text-lg font-bold text-slate-100 mb-2">Send a Message</h3>
          <p class="text-slate-400 text-sm mb-6">
            Leave a message and I will get back to you as soon as possible.
          </p>

          <form @submit.prevent="handleSubmit" class="space-y-4">
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-medium text-slate-300 mb-1.5">Your Name</label>
                <input
                  v-model="formData.name"
                  type="text"
                  required
                  placeholder="e.g. Sarah Jenkins (HR Recruiter)"
                  class="w-full px-4 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-slate-100 placeholder-slate-500 text-sm focus:outline-none focus:border-emerald-500 transition-colors"
                />
              </div>
              <div>
                <label class="block text-xs font-medium text-slate-300 mb-1.5">Your Email</label>
                <input
                  v-model="formData.email"
                  type="email"
                  required
                  placeholder="name@company.com"
                  class="w-full px-4 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-slate-100 placeholder-slate-500 text-sm focus:outline-none focus:border-emerald-500 transition-colors"
                />
              </div>
            </div>

            <div>
              <label class="block text-xs font-medium text-slate-300 mb-1.5">Message / Job Description</label>
              <textarea
                v-model="formData.message"
                required
                rows="4"
                placeholder="Tell me about the role, project, or what you are looking for..."
                class="w-full px-4 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-slate-100 placeholder-slate-500 text-sm focus:outline-none focus:border-emerald-500 transition-colors resize-none"
              ></textarea>
            </div>

            <button
              type="submit"
              class="w-full sm:w-auto inline-flex items-center justify-center gap-2 bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-bold px-6 py-3 rounded-xl transition-all shadow-md shadow-emerald-500/20 hover:shadow-emerald-500/40 cursor-pointer text-sm"
            >
              <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8" />
              </svg>
              <span>Send Inquiry</span>
            </button>

            <!-- Success Alert -->
            <div
              v-if="formSubmitted"
              class="p-3.5 rounded-xl bg-emerald-950/60 border border-emerald-500/50 text-emerald-300 text-xs flex items-center gap-2"
            >
              <svg class="w-4 h-4 text-emerald-400 shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
              </svg>
              <span>Thank you! Your message has been received. I will reply shortly.</span>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>
