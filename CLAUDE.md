# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

SpeakSpark is a WhatsApp-based English learning service by IDNRemote.com. This repo contains a static HTML landing page — no build system, no package manager, no framework.

## Development

Open `index.html` directly in a browser. No server, compilation, or install step needed.

CDN dependencies (loaded at runtime, no local install):
- **Tailwind CSS** — utility classes, configured inline via `tailwind.config`
- **Alpine.js** — reactive UI (mobile nav toggle, FAQ accordion, scroll-triggered floating button)
- **Inter** — font from Google Fonts

## File Structure

- `index.html` — primary landing page (canonical)
- `index2.html` — alternate version / work-in-progress variant
- `images/logo-speakspark.png` — logo asset

## Placeholder Content Still Needed

The page has several items marked with `📸 SCREENSHOT PLACEHOLDER` comments that must be replaced before going live:

| Placeholder | Location | What to replace with |
|---|---|---|
| `og:image` | `<head>` | Real 1200×630px social preview image |
| Screenshot #2 | Feedback section | WhatsApp screenshot: listening exercise feedback |
| Screenshot #3 | Feedback section | WhatsApp screenshot: writing exercise feedback |
| Screenshot #4 | Pronunciation subsection | WhatsApp screenshot: pronunciation score |
| Screenshots #5–7 | Testimonials section | Real buyer testimonials (photo + name + quote) |
| `Rp XX.XXX` | Pricing section | Actual monthly and 3-month prices |
| `+62 XXX-XXXX-XXXX` | Buyer onboarding section | Real SpeakSpark WhatsApp number |
| `https://wa.me/62XXXXXXXXXX` | CTA button | Real WhatsApp deeplink |

## Architecture Notes

- All interactivity is Alpine.js (`x-data`, `x-show`, `x-cloak`, `@click`, `@scroll.window`).
- The `.ss-placeholder` CSS class and its children are styling shims only for development — remove them when replacing with real `<img>` tags.
- The floating "Sudah beli?" button appears after 500px scroll (`window.scrollY > 500`).
- Purchase flow routes to `https://goakal.com/speakspark` (external payment platform).
- The `#mulai` anchor section is the buyer onboarding flow, intentionally separated from the sales content above.

## Target Audience & Goal

**Target:** Profesional Indonesia yang ingin kerja di luar negeri dan ingin jago bahasa Inggris, tapi punya kendala pada kemampuan bahasa Inggris mereka.

**Hot market focus:** Orang yang sudah tahu mereka butuh improve English — langsung dorong ke "Beli". Tidak perlu banyak edukasi, langsung ke action. **Penting: gunakan kata "Beli" bukan "Berlangganan" di semua CTA.**

**Social proof:** 150+ orang yang mau kerja di luar negeri sudah bergabung.

**Tone:** Empati terhadap rasa frustrasi mereka (nggak percaya diri berbahasa Inggris, takut wawancara kerja luar negeri), lalu tunjukkan solusi konkret.

## Prompt (original)

buat landing page

HTML tailwind. if need js, use alpinejs

Mobile first

Inspiration: Blotato

Context:

What is Speak Spark?

Seperti yang sudah kamu tahu, cara kita jadi jago English adalah dengan merutinkannya setiap hari. Tapi ngebangun rutinitas itu nggak mudah kan ya?

Nah karena itulah kami dari tim mentor PJI sudah membuatkan sebuah bot yang akan jadi partner kamu dalam latihan English. Selain membantu ngingetin buat latihan, bot ini juga tempat di mana kamu submit latihan-latihan harian English kamu yang akan direview oleh tim mentor. Jadi selain tim mentor yang pantau, kamu sendiri pun bisa track progress kamu sendiri.

Bot partner ini kami namain SpeakSpark. Kami pilih nama ini karena kami berharap dengan adanya bot ini kamu jadi muncul semangat ("spark") buat enjoy ketika speak English.

Untuk saat ini akses bot ini baru tersedia lewat WhatsApp, jadi kamu submit latihan harian, diingetin, dan berlatih tiap hari via WhatsApp. Beneran kayak latihan English sama teman kamu aja, tapi bedanya kamu latihan sama orang-orang yang memang sudah jago komunikasi English, jadi lebih tahu kebutuhan latihan yang lebih tepat seperti apa.

Kamu bisa nemuin link untuk akses SpeakSpark di LMS-nya GoAkal (Binder) ketika kamu beli kelas privat ini. 😉

Speak Spark main color is purple