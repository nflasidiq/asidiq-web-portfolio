<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const projects = [
  {
    id: 1,
    title: "Rebuild Web System - Telkom Test House",
    category: "Web Apps",
    desc: "Proyek nyata skala perusahaan saat magang di PT AKSII. Bertanggung jawab atas optimasi antarmuka, error handling, serta pembuatan fitur baru pelacakan data riwayat kalibrasi.",
    tags: ["Vue.js", "Tailwind CSS", "JavaScript", "UI Slicing"],
    impact: "100% Responsive Layout & Secured Session Timeout Control",
    featured: false,
    // Path gambar (nanti ganti dengan path di folder public)
    image: "https://placehold.co/800x500/0f172a/34d399?text=Screenshot+Telkom+Test+House",
  },
  {
    id: 2,
    title: "Dasbor Admin Ride-Hailing - Pemuda Express",
    category: "Fullstack",
    desc: "Sistem dasbor internal untuk otomatisasi alur kerja admin, manajemen data transaksi, dan pemantauan aktivitas mitra driver secara real-time (Tugas Akhir Kuliah).",
    tags: ["React.js", "Tailwind CSS", "REST API Integration"],
    impact: "Automated Workflow for Order Recapitulation",
    featured: false,
    image: "https://placehold.co/800x500/0f172a/34d399?text=Screenshot+Dasbor+Pemuda+Express",
  },
  {
    id: 3,
    title: "To-List-an (Tulisan) - Desktop Productivity App",
    category: "Web Apps",
    desc: "Aplikasi produktivitas desktop berbasis Windows untuk menggabungkan fungsi manajemen daftar tugas (to-do list) dan catatan teks biasa secara simultan dalam satu file.",
    tags: ["Electron.js", "JavaScript", "AI-Assisted Development"],
    impact: "Solved Personal Daily Task Efficiency Constraint",
    featured: false,
    image: "https://placehold.co/800x500/0f172a/34d399?text=Screenshot+To-List-an",
  },
];

// Logika untuk Modal (Pop-up Gambar)
const selectedImage = ref(null);
const isModalOpen = ref(false);

const openModal = (imagePath) => {
  selectedImage.value = imagePath;
  isModalOpen.value = true;
  document.body.style.overflow = "hidden"; // Cegah scroll saat modal terbuka
};

const closeModal = () => {
  isModalOpen.value = false;
  setTimeout(() => {
    selectedImage.value = null;
  }, 300); // Tunggu animasi transisi selesai
  document.body.style.overflow = "auto";
};

// Menutup modal dengan tombol 'Escape'
onMounted(() => {
  const handleKeydown = (e) => {
    if (e.key === 'Escape' && isModalOpen.value) closeModal();
  };
  window.addEventListener('keydown', handleKeydown);
  onUnmounted(() => window.removeEventListener('keydown', handleKeydown));
});
</script>

<template>
  <section id="projects" class="py-16 px-4 sm:px-6 relative">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center mb-10">
        <span class="text-xs font-bold uppercase tracking-widest text-emerald-400 bg-emerald-950/60 border border-emerald-800/40 px-3.5 py-1 rounded-full mb-3">
          Featured Work
        </span>
        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-100 tracking-tight">
          Recent <span class="text-emerald-400">Projects</span>
        </h2>
        <p class="mt-4 text-slate-400 max-w-2xl text-sm sm:text-base">
          Kumpulan proyek yang saya kerjakan dengan fokus pada kualitas kode,
          pengalaman pengguna, dan kebutuhan nyata.
        </p>
      </div>

      <!-- Projects Grid -->
      <div class="flex flex-wrap justify-center gap-8">
        <div
          v-for="project in projects"
          :key="project.id"
          class="w-full md:w-[calc(50%-1rem)] bg-slate-900/40 hover:bg-slate-900/70 border border-slate-800/90 hover:border-emerald-500/50 rounded-2xl flex flex-col transition-all duration-300 group hover:-translate-y-1 shadow-lg shadow-black/20 overflow-hidden"
        >
          <!-- Thumbnail Image (Clickable) -->
          <div 
            class="relative w-full aspect-video overflow-hidden cursor-pointer border-b border-slate-800/80"
            @click="openModal(project.image)"
          >
            <!-- Gambar Project -->
            <img 
              :src="project.image" 
              :alt="project.title"
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
            />
            <!-- Overlay Hover (Icon Kaca Pembesar) -->
            <div class="absolute inset-0 bg-slate-950/60 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center backdrop-blur-[2px]">
              <div class="bg-emerald-500 text-slate-950 rounded-full p-3 transform translate-y-4 group-hover:translate-y-0 transition-all duration-300">
                <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0zM10 7v3m0 0v3m0-3h3m-3 0H7" />
                </svg>
              </div>
            </div>
          </div>

          <!-- Card Content -->
          <div class="p-6 sm:p-7 flex flex-col flex-grow">
            <!-- Card Top Bar -->
            <div class="flex items-center justify-between gap-2 mb-4">
              <span class="text-xs font-semibold px-2.5 py-1 rounded-md bg-slate-800 text-slate-300">
                {{ project.category }}
              </span>
              <span
                v-if="project.featured"
                class="text-[11px] font-bold text-emerald-300 bg-emerald-950/60 border border-emerald-800/40 px-2.5 py-0.5 rounded-full flex items-center gap-1"
              >
                ★ Featured
              </span>
            </div>

            <h3 class="text-xl font-bold text-slate-100 group-hover:text-emerald-400 transition-colors mb-2">
              {{ project.title }}
            </h3>

            <p class="text-slate-400 text-sm leading-relaxed mb-4 flex-grow">
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
            <div class="flex flex-wrap gap-1.5 mt-auto">
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

    <!-- Modal Lightbox (Layar Penuh) -->
    <transition
      enter-active-class="transition-opacity duration-300 ease-out"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="transition-opacity duration-200 ease-in"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <div 
        v-if="isModalOpen" 
        class="fixed inset-0 z-[100] flex items-center justify-center p-4 sm:p-8 bg-slate-950/90 backdrop-blur-sm"
        @click="closeModal"
      >
        <!-- Tombol Close -->
        <button 
          @click.stop="closeModal"
          class="absolute top-6 right-6 sm:top-8 sm:right-8 p-2 rounded-full bg-slate-800 text-slate-300 hover:text-emerald-400 hover:bg-slate-700 transition-colors"
        >
          <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>

        <!-- Container Gambar (Klik di gambar tidak akan menutup modal) -->
        <div 
          class="relative max-w-5xl w-full max-h-[85vh] rounded-xl overflow-hidden shadow-2xl border border-slate-700/50"
          @click.stop
        >
          <img 
            :src="selectedImage" 
            alt="Full Project Screenshot"
            class="w-full h-full object-contain bg-slate-900"
          />
        </div>
      </div>
    </transition>
  </section>
</template>
