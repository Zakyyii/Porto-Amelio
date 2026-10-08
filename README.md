# 📖 Panduan Kustomisasi Website Portofolio

Semua data yang perlu diubah terpusat di beberapa file. Kamu **tidak perlu** menyentuh kode komponen — cukup ubah file data berikut.

---

## 📁 Struktur File Penting

```
portfolio/
├── src/
│   └── data/
│       ├── profile.js      ← ✅ UBAH INI: nama, foto, sekolah, sosmed, dll
│       ├── skills.js       ← ✅ UBAH INI: daftar keahlian & tools
│       └── achievements.js ← ✅ UBAH INI: daftar prestasi/pencapaian
└── public/
    ├── images/
    │   ├── profile/
    │   │   ├── profile.webp       ← ✅ Ganti dengan foto profilmu (utama, grayscale)
    │   │   └── profile-2.webp     ← ✅ Ganti dengan foto profilmu (alternatif, berwarna)
    │   ├── org/
    │   │   ├── osis-1.webp ~ osis-5.webp  ← ✅ Foto kegiatan OSIS
    │   │   └── mpk-1.webp  ~ mpk-5.webp   ← ✅ Foto kegiatan MPK
    │   └── achievements/
    │       ├── ach-1.webp  ← ✅ Foto/sertifikat pencapaian 1
    │       ├── ach-2.webp  ← ✅ Foto/sertifikat pencapaian 2
    │       └── ach-3.webp  ← ✅ Foto/sertifikat pencapaian 3
    └── cv/
        └── CV_NamaAnda.pdf  ← ✅ Ganti dengan file CV kamu
```

---

## 👤 1. Mengubah Nama, Sekolah, dan Data Diri

Buka file: `src/data/profile.js`

```js
export const profile = {
  name: "Nama Lengkapmu",           // ← Ganti nama lengkap
  nim: "12345678",                  // ← Ganti NIM/No. Induk Siswa
  maskNim: false,                   // ← Set true untuk menyembunyikan sebagian NIM
  major: "Rekayasa Perangkat Lunak", // ← Ganti program studi / jurusan
  headline: "Siswa aktif yang...",  // ← Kalimat singkat (maks 90 karakter)
  description: "Tuliskan 80-150 kata tentang dirimu...",

  photo: "/images/profile/profile.webp",
  photoAlt: "/images/profile/profile-2.webp",

  education: [
    {
      level: "S1",                         // ← S1, SMA, SMP, SD, dll
      institution: "Universitas ...",      // ← Nama sekolah/universitas
      startYear: 2022,
      endYear: "Sekarang",
    },
    {
      level: "SMA",
      institution: "SMA Negeri ...",
      startYear: 2019,
      endYear: 2022,
    },
    // Tambahkan atau hapus entri sesuai kebutuhan
  ],
};
```

---

## 📸 2. Mengganti Foto Profil

1. Siapkan **2 foto** dalam format `.webp` (atau `.jpg`/`.png` — ubah ekstensi di `profile.js`)
2. Simpan ke:
   - `public/images/profile/profile.webp` → foto utama (tampil hitam-putih)
   - `public/images/profile/profile-2.webp` → foto alternatif (tampil berwarna saat hover)
3. Ukuran yang disarankan: **400×500 px** (rasio 4:5)

> **Tips konversi ke WebP:** Gunakan [squoosh.app](https://squoosh.app) atau [cloudconvert.com](https://cloudconvert.com/jpg-to-webp)

---

## 🔗 3. Mengubah Sosial Media & Kontak

Masih di `src/data/profile.js`, cari bagian `contact`:

```js
contact: {
  linkedin:  "https://www.linkedin.com/in/username-kamu",
  instagram: "https://www.instagram.com/username-kamu",
  email:     "emailkamu@gmail.com",
  phone:     "+6281234567890",
  whatsapp:  "https://wa.me/6281234567890", // ← Nomor tanpa + dan 0 awal → 62xxx
  cvFile:    "/cv/CV_NamaKamu.pdf",
},
```

> Jika tidak punya akun tertentu, biarkan nilainya `""` — tombol tidak akan muncul.

---

## 🏆 4. Mengubah Daftar Pencapaian/Prestasi

Buka file: `src/data/achievements.js`

```js
export const achievements = [
  {
    id: 1,
    title: "Juara 1 Olimpiade Matematika",
    year: 2025,
    organization: "Dinas Pendidikan Kota",
    description: "Deskripsi singkat, maks 2 kalimat.",
    image: "/images/achievements/ach-1.webp",
  },
  // Tambah atau kurangi entri sesuai kebutuhan
];
```

Simpan foto/sertifikat ke `public/images/achievements/ach-1.webp`, `ach-2.webp`, dst.

---

## 🛠️ 5. Mengubah Keahlian & Tools

Buka file: `src/data/skills.js`

```js
export const skills = [
  { id: 1, name: "HTML & CSS",      category: "technical" },
  { id: 2, name: "JavaScript",      category: "technical" },
  { id: 3, name: "Komunikasi",      category: "soft" },
  { id: 4, name: "Manajemen Waktu", category: "soft" },
];

export const tools = [
  { id: 1, name: "Figma",      icon: "SiFigma" },
  { id: 2, name: "JavaScript", icon: "SiJavascript" },
  { id: 3, name: "React",      icon: "SiReact" },
  { id: 4, name: "Python",     icon: "SiPython" },
  { id: 5, name: "GitHub",     icon: "SiGithub" },
];
```

**Icon yang tersedia:** `SiFigma`, `SiJavascript`, `SiReact`, `SiTailwindcss`, `SiPython`, `SiGithub`, `SiNodedotjs`, `SiVuedotjs`, `SiFlutter`, `SiDart`, dll.

---

## 🖼️ 6. Mengubah Foto Kegiatan Organisasi

Masih di `src/data/profile.js`, cari bagian `activities`:

```js
activities: [
  {
    id: "osis",
    title: "OSIS",           // ← Nama organisasi (tampil di tombol tab)
    role: "Ketua Umum",      // ← Jabatanmu
    period: "2023 - 2024",
    description: "Keterangan singkat kontribusimu.",
    photos: [
      {
        src: "/images/org/osis-1.webp",
        program: "Nama Program Kerja",
        desc: "Deskripsi kegiatan singkat.",
      },
      // Tambah atau kurangi foto sesuai kebutuhan (tidak harus 5)
    ],
  },
  // Tambah organisasi lain: Pramuka, ROHIS, dll
  {
    id: "pramuka",
    title: "Pramuka",
    role: "Pradana",
    period: "2022 - 2023",
    description: "...",
    photos: [ ... ],
  },
],
```

**Ukuran foto organisasi yang disarankan:** `800×600 px` (landscape, format webp)

---

## 📄 7. Mengganti File CV

1. Buat/ekspor CV dalam format `.pdf`
2. Simpan ke: `public/cv/CV_NamaKamu.pdf`
3. Perbarui path di `profile.js`:
   ```js
   cvFile: "/cv/CV_NamaKamu.pdf",
   ```

---

## 🚀 8. Cara Menjalankan Website

Pastikan sudah menginstal **Node.js** (versi 18+) dari [nodejs.org](https://nodejs.org).

```bash
# Masuk ke folder portfolio
cd portfolio

# Install dependencies (cukup sekali)
npm install

# Jalankan di mode development (buka http://localhost:5173)
npm run dev

# Build untuk produksi
npm run build
```

---

## 🎨 9. Mengubah Warna Tema

Buka `src/styles/index.css` dan ubah nilai di bagian `@theme`:

```css
@theme {
  --color-accent: #9a3a1a;   /* Warna aksen (merah bata) */
  --color-ink: #1c1815;      /* Warna teks utama */
  --color-surface: #f5efe4;  /* Warna background */
  --color-muted: #7a7068;    /* Warna teks sekunder */
}
```

---

## ❓ FAQ

**Q: Foto tidak muncul?**
Pastikan nama file **persis sama** (huruf besar/kecil berbeda di Linux) dan disimpan di folder `public/` yang benar.

**Q: Mau tambah/hapus tab organisasi?**
Tambah atau hapus objek di array `activities` dalam `profile.js`. Tombol tab akan menyesuaikan otomatis.

**Q: Bisa ganti font?**
Buka `src/styles/index.css` dan ganti `"Source Serif 4"` dengan nama font dari Google Fonts yang kamu inginkan, lalu tambahkan link importnya di `index.html`.
