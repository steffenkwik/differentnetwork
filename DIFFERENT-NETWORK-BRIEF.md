# MASTER BRIEF — Website Utama Different Network

> Dokumen ini adalah konteks lengkap untuk membangun **website utama Different Network** dari nol.
> Cukup copy-paste seluruh isi file ini ke dalam chat Claude Code baru (di repository baru),
> dan AI akan langsung paham siapa kita, apa yang kita develop, dan website seperti apa yang harus dibuat.
>
> Tema visual MENGIKUTI website personal Steffen Kwik (steffenkwik.pages.dev) yang sudah jadi,
> tapi ISI dan FOKUS-nya untuk perusahaan Different Network sebagai sorotan utama.

---

## 1. SIAPA KITA

**Different Network** adalah perusahaan dan komunitas AI #1 di Indonesia.
Kami membangun gerakan untuk membuat masyarakat Indonesia melek dan mahir AI —
bukan sekadar jadi penonton di era kecerdasan buatan, tapi jadi pelaku yang menentukan nasibnya sendiri.

- **Nama perusahaan:** Different Network
- **Founder:** Steffen Kwik (AI Builder, Indonesia)
- **Posisi:** Komunitas & ekosistem pembelajaran AI #1 di Indonesia
- **Website personal founder (sudah jadi, jadi acuan tema):** steffenkwik.pages.dev
- **Website program sertifikasi:** https://differentnetworkai.com
- **Server Discord (komunitas inti):** https://discord.gg/BU8BbvjA

### Keyakinan inti (manifesto)
- "Bukan sekadar platform. Ini gerakan."
- Indonesia sedang tertinggal di bidang AI — dan mayoritas orang belum sadar.
- Di tengah banjir konten AI penuh hype kosong dan janji palsu, kami memilih jalan berbeda:
  jujur, tajam, berbasis data, dan selalu berpihak pada komunitas — bukan tren, bukan sponsor.
- "Orang yang menguasai AI hari ini akan menentukan nasibnya sendiri esok hari.
  Yang tidak, akan jadi alat bagi yang menguasainya."
- "Di masa depan, bukan AI yang akan menggantikan pekerjaanmu — tapi orang yang bisa menggunakan AI." ~ Steffen Kwik

---

## 2. APA YANG KITA DEVELOP UNTUK INDONESIA

Different Network membangun ekosistem AI menyeluruh untuk Indonesia:

1. **Komunitas AI #1 Indonesia** — server Discord aktif 24/7, gratis, tempat para builder, kreator,
   dan inovator berbagi insight, berkolaborasi, dan tumbuh bersama.
2. **Program "Jadi Praktisi AI Bersertifikat"** — kurikulum berbasis praktik nyata, dari nol hingga mahir.
   - Kuasai AI dari nol hingga mahir dengan kurikulum berbasis praktik nyata.
   - Bangun skill AI yang sesuai dengan karir dan bisnis.
   - Output lebih cepat tanpa pengulangan yang buang waktu.
3. **Konten & edukasi AI** — YouTube, Instagram, TikTok, X, LinkedIn (jujur, tajam, anti-hype).
4. **Fokus teknologi:** Agentic AI, Neural Networks, LLMs, Automation, Machine Learning, Humanoid AI,
   Prompt Engineering, Computer Vision, Deep Learning, Multi-Agent Systems, RAG Pipelines, Fine-Tuning,
   Workflow Automation, Generative AI, AI Voice Agents, Image Generation, MCP Servers, Vibe Coding,
   Data Analytics, AI Integrations.
5. **Ekosistem tools yang kami pakai & ajarkan:** Claude, ChatGPT, Grok, Gemini, OpenClaw, NotebookLM,
   Zapier, n8n, Make.com, Manus.

---

## 3. TUJUAN WEBSITE BARU INI

Membangun **website UTAMA Different Network** — bukan link-in-bio personal lagi, tapi situs perusahaan
yang menjadi sorotan utama brand. Tetap satu halaman (single-page), polished, kelas production,
dengan estetika AI/agentic yang sama, TAPI:

- **Fokus ke perusahaan**, bukan ke pribadi Steffen Kwik (Steffen tetap muncul sebagai Founder).
- Menonjolkan: misi/gerakan, program sertifikasi, komunitas Discord, value proposition,
  bukti sosial (jumlah member, testimoni), dan ajakan bergabung.
- CTA utama: **Gabung program sertifikasi (differentnetworkai.com)** dan **Join Discord**.

### Struktur konten yang disarankan untuk website Different Network
1. **Hero** — Logo Different Network besar, tagline "Komunitas AI #1 Indonesia",
   sub "Bukan sekadar platform. Ini gerakan." + 2 tombol CTA (Gabung Sekarang / Join Discord).
2. **Strip skill AI berjalan** (marquee) — daftar kapabilitas AI (lihat poin 4 di atas).
3. **Manifesto / Misi** — kenapa kita ada, keyakinan inti (teks dari bagian 1).
4. **Program Sertifikasi "Jadi Praktisi AI Bersertifikat"** — headline + 3 benefit + tombol Gabung.
5. **Komunitas Discord** — kartu hero Discord dengan stats (#1 AI Community ID, 24/7 Active, FREE).
6. **Powered by · AI Ecosystem** — slider logo tools AI.
7. **Founder spotlight** — Steffen Kwik sebagai Founder + quote, link ke website personal.
8. **Quote card interaktif** (swap animasi) — "Fortune Favors The Bold ~ Virgil" ⇄ quote Steffen.
9. **Sosial media** — grid 6 tile (YouTube, Instagram, TikTok, X, LinkedIn, Discord).
10. **Ending / kontak** — logo, manifesto penutup, sosial, business inquiries (email + Telegram),
    divider, copyright "Different Network · © 2026 All rights reserved" + Privacy Policy.
11. **Floating CTA** — tombol melayang "MULAI BERGERAK SEKARANG!".

---

## 4. PRINSIP & SISTEM DESAIN (WAJIB DIIKUTI — diambil dari website Steffen Kwik)

### Brand & warna
```
--black:    #000   (background murni hitam, WAJIB pure black, bukan abu-abu)
--white:    #fff
--orange:   #ff4d00  (aksen utama brand)
--orange-2: #ff7a3d  (aksen sekunder / gradient)
```
Glass surfaces (kaca transparan di atas hitam):
```
--glass:    rgba(255,255,255,.045)
--glass-2:  rgba(255,255,255,.08)
--line:     rgba(255,255,255,.1)
--txt:      rgba(255,255,255,.96)
--muted:    rgba(255,255,255,.5)
```

### Font (Google Fonts)
```
--f-disp: 'Chakra Petch'  (display / judul, letter-spacing lebar, futuristik)
--f-ui:   'Space Grotesk' (body / UI)
--f-mono: 'Space Mono'    (label kecil, mono, uppercase, letter-spacing lebar)
```
Easing standar: `cubic-bezier(.22,.61,.36,1)`

### Estetika & elemen khas
- **Estetika AI/agentic, neural network, futuristik.** Latar hitam pekat + aksen oranye menyala (glow).
- **Boot screen** `position:fixed` saat load: logo brand + progress bar oranye + teks mono berganti
  ("BOOTING SYSTEM" → "LOADING NEURAL NET" → "SYNCING NODES" → "READY"), lalu fade out.
- **Canvas neural network** animasi di latar (titik-titik node + garis penghubung, reaktif ke mouse).
- **Smoke/fog oranye** drifting di latar (blob blur besar, sangat subtle, TIDAK PERNAH menutupi teks).
  Hanya floor tipis oranye di dasar layar.
- **Bento grid** — kartu-kartu (tile) dengan glass background, border tipis, sudut "corner brackets"
  dekoratif, dan neon glow oranye saat hover.
- **Glow tile:** default `box-shadow:0 0 0 1px rgba(255,77,0,.05),0 0 18px -3px rgba(255,77,0,.1)`,
  hover lebih terang + lift shadow.
- **Slider/marquee** horizontal yang bisa digeser (skill chips & logo AI), dengan tombol ‹ ›.
- **Quote card swap interaktif** — foto/teks berganti saat hover/tap, plus AUTO-CYCLE tiap beberapa detik
  (gambar utama tampil ~5-6 dtk, alternatif tampil singkat ~2 dtk, lalu kembali). Pause saat hover/tab hidden.
- **Reveal on scroll** — elemen muncul dengan `animation-delay` bertahap (stagger).
- **Floating CTA** melayang (koin logo + banner teks miring).
- **Toast** konfirmasi (mis. "Email disalin!") saat klik email.

### Aturan teknis WAJIB (pelajaran dari proyek sebelumnya)
1. **Single-file HTML** — seluruh situs di satu `index.html` (CSS & JS inline). Mudah deploy ke Cloudflare Pages.
2. **PURE BLACK `#000`** untuk semua background gelap. Jangan pernah ada abu-abu nyasar.
   - Hati-hati: `.tile:hover` jangan set background abu-abu kalau tile itu dipakai untuk swap —
     paksa `background:#000` pada kartu quote.
3. **Tidak ada em dash (—) di teks apa pun** (terlihat AI-generated). Pakai `-` untuk kalimat,
   `~` untuk atribusi quote (mis. "~ Virgil").
4. **Gambar di atas hitam:** pakai **WebP lossless** (lossy bikin artefak abu-abu di area hitam).
   Untuk foto orang, pakai **alpha radial elliptical feather** (bukan tepi kotak) supaya tidak ada "kotak".
   Selalu sediakan `.webp` + fallback `.png` via `<picture>`.
5. **Tidak ada custom cursor** — pakai cursor default OS.
6. **No horizontal scroll di mobile:** `html{overflow-x:hidden;width:100%}`, hindari trik full-bleed `100vw`
   yang overflow karena padding shell. Constrain gambar besar dengan `max-width` + `margin auto`.
7. **Boot screen harus center sempurna di mobile:** beri `width:100vw;height:100dvh;left:0;top:0` eksplisit.
8. **Logo AI gelap** (ChatGPT/Grok/Manus) tak terlihat di hitam → bungkus dengan pill putih
   (`background:#fff;border-radius:11px;padding:7px 12px`).
9. **Responsif:** breakpoint mobile `max-width:560px`, desktop `min-width:980px`. Pakai `clamp()` untuk skala.
10. **Aksesibilitas:** `:focus-visible` outline oranye, `aria-label` pada link/tombol ikon,
    hormati `prefers-reduced-motion` (matikan animasi berat).
11. **Verifikasi dengan screenshot** (mis. Playwright headless) sebelum dianggap selesai — cek mobile & desktop.

### Aset gambar yang perlu disiapkan (taruh di root repo)
- `logo.webp` / `logo-mark.png` — logo Different Network (favicon + di hero/footer).
- `steffen.webp/png` — foto Founder (Steffen Kwik), alpha feather di hitam.
- Logo tools AI (pill putih): `claude.png`, `chatgpt.png`, `grok.png`, `gemini.png`, `openclaw.png`,
  `notebooklm.png`, `zapier.png`, `n8n.png`, `make.png`, `Manus-ai-agent-logo.png`.
- Opsional: `virgil.webp/png` (patung Virgil untuk quote card), visual hero/laptop.

---

## 5. LINK & DATA RESMI (pakai persis ini)

| Item | URL / Nilai |
|------|-------------|
| Program sertifikasi (CTA utama) | https://differentnetworkai.com |
| Discord (komunitas) | https://discord.gg/BU8BbvjA |
| YouTube | https://youtube.com/@steffenkwik |
| Instagram | https://www.instagram.com/steffenkwik |
| TikTok | https://www.tiktok.com/@steffenkwik.ai |
| X (Twitter) | https://x.com/SteffenKwik |
| LinkedIn | https://www.linkedin.com/in/steffen-kwik-b3b106238 |
| Telegram (bisnis) | https://t.me/kwikste |
| Email bisnis | steffenkwik@gmail.com |
| Website personal Founder | https://steffenkwik.pages.dev |

---

## 6. LANGKAH DARI NOL (di Claude Code chat baru + repository baru)

1. **Buat repository GitHub baru**, mis. `different-network-web` (public).
2. **Buka Claude Code di repo baru** (web/desktop/CLI). Pastikan environment punya akses ke repo itu.
3. **Paste PROMPT di bagian 7** sebagai pesan pertama. AI akan punya seluruh konteks dari dokumen ini.
4. Upload aset gambar (logo Different Network + foto + logo AI) ke root repo.
5. Biarkan AI membangun `index.html` single-file mengikuti prinsip desain di bagian 4.
6. **Preview lokal:** buka `index.html` di browser (atau `python -m http.server`), cek mobile & desktop.
7. **Deploy ke Cloudflare Pages:** connect repo ke Cloudflare Pages, branch produksi `main`,
   build command kosong, output directory `/` (root). Auto-deploy tiap push ke `main`.
   (Catatan: GitHub Pages sempat gagal "Resource not accessible" karena belum di-enable manual —
   Cloudflare Pages lebih lancar untuk situs statis ini.)
8. Iterasi: minta AI perbaiki detail sambil verifikasi via screenshot.

---

## 7. PROMPT SIAP COPY-PASTE (kirim sebagai pesan pertama di chat baru)

```
Halo, saya Steffen Kwik, Founder Different Network — komunitas & ekosistem AI #1 di Indonesia.

Saya mau kamu membangun WEBSITE UTAMA perusahaan Different Network dari nol, dalam satu file
index.html (HTML + CSS + JS inline), siap deploy ke Cloudflare Pages.

Konteks lengkap siapa kita, apa yang kita develop untuk Indonesia, struktur konten, dan SELURUH
prinsip desain ada di dokumen "MASTER BRIEF — Website Utama Different Network" yang saya tempel
di bawah. Ikuti dokumen itu persis, terutama bagian "PRINSIP & SISTEM DESAIN".

Tema visual harus SE-TEMA dengan website personal saya steffenkwik.pages.dev (latar hitam pekat #000,
aksen oranye #ff4d00, putih #fff; font Chakra Petch / Space Grotesk / Space Mono; estetika AI/agentic,
neural network, boot screen, smoke oranye subtle, bento grid glass, glow oranye, slider geser,
quote card swap dengan auto-cycle, floating CTA). TAPI isinya untuk PERUSAHAAN Different Network
sebagai sorotan utama (bukan link-in-bio personal). Steffen Kwik tetap tampil sebagai Founder.

Aturan wajib: pure black #000 (jangan ada abu-abu nyasar), TIDAK ADA em dash di teks (pakai - dan ~),
gambar WebP lossless + fallback PNG via <picture>, tidak ada custom cursor, no horizontal scroll di
mobile, responsif (mobile <=560px, desktop >=980px), aksesibel (focus-visible, aria-label,
prefers-reduced-motion). Verifikasi hasil dengan screenshot mobile & desktop sebelum selesai.

Mulai dengan menyusun struktur halaman (lihat bagian 3 dokumen), lalu bangun index.html lengkap.
Tanyakan ke saya kalau ada aset/logo yang perlu saya upload.

--- DOKUMEN MASTER BRIEF ---
[TEMPEL SELURUH ISI FILE DIFFERENT-NETWORK-BRIEF.md DI SINI]
```

---

*Dibuat sebagai acuan transisi dari website personal Steffen Kwik ke website utama Different Network.*
*Tema sama, isi berbeda, prinsip dipertahankan.*
