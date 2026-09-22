# Naufal Asidiq — Portfolio

Website portfolio personal **Naufal Asidiq**, Junior Front-End Developer lulusan
Teknik Informatika Polban. Website ini menampilkan profil, kemampuan teknis,
proyek yang pernah dikerjakan, serta informasi kontak untuk kebutuhan
rekrutmen, kerja sama, dan kolaborasi.

## Tentang Proyek

Portfolio ini dibuat sebagai single-page website dengan tampilan dark modern,
aksen emerald, dan layout responsif. Konten utama yang tersedia:

- Hero section dengan ringkasan profil, metrik pengalaman, tech stack, dan
  tombol menuju proyek serta CV.
- About section berisi latar belakang, cara kerja, lokasi, model kerja, dan
  kekuatan utama.
- Skills section dengan daftar skill berdasarkan kategori dan tingkat
  penguasaan.
- Projects section yang menampilkan tiga proyek:
  - **Rebuild Web System — Telkom Test House**
  - **Dasbor Admin Ride-Hailing — Pemuda Express**
  - **To-List-an (Tulisan) — Desktop Productivity App**
- Galeri proyek berbentuk modal slider yang mendukung navigasi tombol dan
  keyboard (`ArrowLeft`, `ArrowRight`, dan `Escape`).
- Contact section dengan foto profil, fitur menyalin alamat email, serta tautan
  GitHub dan LinkedIn.
- Navbar responsif dengan menu desktop/mobile, status “Available for hire”,
  dan navigasi anchor ke setiap section.
- Tombol **Back to top** pada footer.

## Teknologi

- [Vue.js 3](https://vuejs.org/)
- [Vite](https://vite.dev/)
- [Tailwind CSS v4](https://tailwindcss.com/)
- JavaScript dengan Composition API dan `<script setup>`
- HTML5, CSS3, dan Google Fonts (Plus Jakarta Sans)

## Persyaratan

- Node.js dan npm

## Menjalankan Secara Lokal

1. Clone repository dan masuk ke folder proyek:

   ```bash
   git clone https://github.com/nflasidiq/asidiq-web-portfolio.git
   cd asidiq-web-portfolio
   ```

2. Install dependency:

   ```bash
   npm install
   ```

3. Jalankan development server:

   ```bash
   npm run dev
   ```

   Buka URL yang ditampilkan Vite, biasanya
   `http://localhost:5173`.

## Perintah yang Tersedia

| Perintah          | Keterangan                                      |
| ----------------- | ----------------------------------------------- |
| `npm run dev`     | Menjalankan development server dengan Vite      |
| `npm run build`   | Membuat build production ke folder `dist/`      |
| `npm run preview` | Menjalankan preview dari hasil build production |

## Struktur Direktori

```text
.
├── public/
│   ├── cv/                  # File CV yang dapat dibuka dan diunduh
│   ├── projects/            # Screenshot proyek untuk galeri
│   ├── profile.jpeg         # Foto profil
│   └── iconNA.png           # Favicon
├── src/
│   ├── components/
│   │   ├── AboutSection.vue
│   │   ├── ContactSection.vue
│   │   ├── FooterSection.vue
│   │   ├── HeroSection.vue
│   │   ├── Navbar.vue
│   │   ├── ProjectsSection.vue
│   │   └── SkillsSection.vue
│   ├── App.vue              # Komposisi halaman utama
│   ├── main.js              # Entry point aplikasi Vue
│   └── style.css            # Import Tailwind CSS
├── index.html               # Metadata dan entry HTML
├── vite.config.js           # Konfigurasi Vite dan plugin Tailwind
└── package.json
```

## Kustomisasi Konten

Konten portfolio disimpan langsung di komponen Vue terkait:

- Informasi profil dan CV: `src/components/HeroSection.vue`
- Data pengalaman dan kekuatan: `src/components/AboutSection.vue`
- Daftar skill: `src/components/SkillsSection.vue`
- Data proyek dan screenshot: `src/components/ProjectsSection.vue`
- Email dan tautan sosial: `src/components/ContactSection.vue`
- Navigasi anchor: `src/components/Navbar.vue`

File di dalam `public/` dapat direferensikan dari root URL, misalnya
`/profile.jpeg` atau `/projects/PE/Portfolio FE.png`.

## Build Production

Untuk memeriksa hasil production secara lokal:

```bash
npm run build
npm run preview
```

Hasil build berada di folder `dist/` dan dapat dipublikasikan pada layanan
hosting statis yang mendukung aplikasi Vite.

## Kontak

- Email: [naufalasidiq150@gmail.com](mailto:naufalasidiq150@gmail.com)
- GitHub: [github.com/nflasidiq](https://github.com/nflasidiq)
- LinkedIn:
  [Naufal Asidiq](https://www.linkedin.com/in/naufal-asidiq-0876b2298/)
