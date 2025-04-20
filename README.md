# Project Fonts

> Kumpulan file font yang digunakan di proyek Next.js saya, termasuk berbagai varian dan tipe dari setiap font.

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)]()

---

## 🔖 About

Repositori ini berisi koleksi **semua font** yang dipakai dalam proyek Next.js saya, setiap font diatur dalam folder terpisah dengan struktur varian (Extralight, Regular, Bold, dll.). Semua font tersedia melalui:

- **Raw GitHub** (`raw.githubusercontent.com`)  
- **jsDelivr CDN** (`cdn.jsdelivr.net`)

Sehingga mudah diintegrasikan ke dalam aplikasi web.

**Repository topics**: `fonts`, `webfonts`, `nextjs`, `font-assets`, `cdn`

---

## 🎨 Preview Contoh

> Contoh menggunakan font **PP Mori Extralight**:

```html
<style>
  @font-face {
    font-family: "PP Mori";
    src: url("https://cdn.jsdelivr.net/gh/Fapzarz/Font@main/fonts/pp-mori/extralight/pp-mori-extralight.otf") format("opentype");
    font-weight: 200;
    font-style: normal;
  }
  .preview {
    font-family: "PP Mori", sans-serif;
    font-weight: 200;
    font-size: 2rem;
  }
</style>
<p class="preview">The quick brown fox jumps over the lazy dog</p>
```

> **Ganti** folder `pp-mori` dan file sesuai font lain (misal `fonts/another-font/...`).

---

## 📂 Struktur Direktori

```
/ (root)
├─ fonts/                  # Koleksi semua font
│   ├─ pp-mori/
│   │    ├─ extralight/    # varian Extralight
│   │    │    └─ pp-mori-extralight.otf
│   │    ├─ regular/       # varian Regular
│   │    │    └─ pp-mori-regular.otf
│   │    └─ bold/          # varian Bold
│   │         └─ pp-mori-bold.otf
│   └─ another-font/       # contoh font lain
│        ├─ light/
│        ├─ regular/
│        └─ bold/
├─ LICENSE
└─ README.md
```

---

## 🚀 Getting Started

### 1. Clone Repo

```bash
git clone https://github.com/Fapzarz/Font.git
cd Font
```

### 2. Pasang via CSS (`@font-face`)

Tambahkan kode di file CSS global (misal `styles/globals.css`):

```css
@font-face {
  font-family: "Nama Font";
  font-style: normal;
  font-weight: 400;
  src: url("https://cdn.jsdelivr.net/gh/Fapzarz/Font@main/fonts/<font-name>/<varian>/<file>.<ext>") format("opentype");
}
```

Ganti `<font-name>`, `<varian>`, dan `<file>.<ext>` sesuai struktur.

### 3. Integrasi di Next.js

#### a. Menggunakan CSS Global

Import `globals.css` di `pages/_app.js` atau `app/layout.tsx`:

```js
import '../styles/globals.css';
```

#### b. Menggunakan `next/font/local` (Next 13+)

```tsx
// app/layout.tsx
import localFont from 'next/font/local';

const myFonts = localFont({
  src: [
    // Contoh PP Mori
    { path: 'https://cdn.jsdelivr.net/gh/Fapzarz/Font@main/fonts/pp-mori/extralight/pp-mori-extralight.otf', weight: '200', style: 'normal' },
    { path: 'https://cdn.jsdelivr.net/gh/Fapzarz/Font@main/fonts/pp-mori/regular/pp-mori-regular.otf', weight: '400', style: 'normal' },
    // Tambahkan font lainnya di sini
  ],
  variable: '--font-primary'
});

export default function RootLayout({ children }) {
  return (
    <html lang="en" className={myFonts.variable}>
      <body>{children}</body>
    </html>
  );
}
```

Lalu di CSS:

```css
body {
  font-family: var(--font-primary), sans-serif;
}
```

---

## ☁️ CDN & Raw URLs

- **Raw GitHub**:  
  `https://raw.githubusercontent.com/Fapzarz/Font/main/fonts/<font-name>/<varian>/<file>.<ext>`
- **jsDelivr**:  
  `https://cdn.jsdelivr.net/gh/Fapzarz/Font@main/fonts/<font-name>/<varian>/<file>.<ext>`

> Sesuaikan placeholder dengan nama folder dan file.

---

## 📝 License

Periksa `LICENSE` di root untuk lisensi tiap font (Open Font License, proprietary, dll.).

---

## 🤝 Contributing

1. Fork repo ini
2. Buat branch: `git checkout -b feature/fonts/<nama-font>`
3. Tambah folder font di `fonts/<nama-font>`
4. Commit: `git commit -m "chore(fonts): add <nama-font> varian <varian>"`
5. Push: `git push origin feature/fonts/<nama-font>`
6. Buka Pull Request

---

## 📬 Kontak

- **Repo**: https://github.com/Fapzarz/Font

---

_Last updated: 2025-04-20_

