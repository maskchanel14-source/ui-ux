# ui-ux

Kumpulan Agent Skill UI/UX yang dipasang pada **project scope**, sehingga ikut tersimpan di repository dan dapat dipakai oleh coding agent yang mendukung format `SKILL.md`.

## Skill yang terpasang

| Skill | Sumber | Kegunaan |
| --- | --- | --- |
| `design-taste-frontend` | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) | Art direction dan pemeriksaan visual untuk frontend |
| `web-design-guidelines` | [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) | Audit UI/UX dan aksesibilitas dengan checklist Vercel |
| `awesome-design-md` | [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) | 84 referensi `DESIGN.md` lokal, dengan wrapper Agent Skill |
| `screenshot-to-code` | [OneWave-AI/claude-skills](https://github.com/OneWave-AI/claude-skills) | Mengubah screenshot/mockup menjadi frontend dan membandingkan hasil render |
| `playwright-cli` | [microsoft/playwright-cli](https://github.com/microsoft/playwright-cli) | Automasi browser, pengujian, dan screenshot melalui Playwright |

Skill canonical berada di `.agents/skills/`. Tautan di `.claude/skills/` membuat skill yang sama tersedia untuk Claude Code tanpa menduplikasi isi. Empat skill upstream dicatat di `skills-lock.json`; sumber dan revisi Awesome DESIGN.md dicatat di `.agents/skills/awesome-design-md/SOURCE.md`.

## Setup Playwright

Persyaratan: Node.js 22.20 atau lebih baru.

```bash
npm install
# Jalankan sekali jika Chromium belum tersedia (memerlukan akses ke CDN Playwright)
npx playwright install chromium
npx --no-install playwright-cli --help
```

Perintah browser berikut memakai binary lokal dari `devDependencies`, jadi instalasi global tidak diperlukan:

```bash
npx --no-install playwright-cli open https://example.com
npx --no-install playwright-cli snapshot
npx --no-install playwright-cli screenshot --filename=example.png
npx --no-install playwright-cli close
```

Taste Skill juga memiliki pemeriksaan browser opsional yang membutuhkan Chrome, Edge, atau Chromium pada mesin yang menjalankannya.

## Contoh prompt

- **Taste:** “Buat landing page yang original dan terasa premium, lalu periksa hasil render-nya.”
- **Vercel checklist:** “Gunakan `web-design-guidelines` untuk audit `src/components/**/*`.”
- **Awesome DESIGN.md:** “Gunakan `awesome-design-md`, pilih referensi Stripe, dan terapkan pada halaman pricing.”
- **Screenshot to Code:** “Implementasikan screenshot terlampau di stack project ini, lalu bandingkan hasil render-nya.”
- **Playwright:** “Gunakan `playwright-cli` untuk menguji alur utama pada tiga ukuran viewport.”

## Verifikasi dan update

```bash
npm run skills:list
npm run skills:update
```

`skills:update` mengelola empat skill yang tercatat di `skills-lock.json`. Wrapper dan library `awesome-design-md` di-pin dan diperbarui secara terpisah sesuai petunjuk pada `SOURCE.md` miliknya.

Lihat `THIRD_PARTY_NOTICES.md` untuk asal-usul dan lisensi komponen pihak ketiga.
