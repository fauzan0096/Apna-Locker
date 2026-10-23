# Apna Locker

Kaagzaat ek jagah: photo rakho, naam se dhundho, expiry ki tareekh ki yaad pao, aur sarkari yojnayein dekho. Hinglish mein, phone par installable app (PWA).

## Files

| File | Kaam |
|---|---|
| `index.html` | Poori app (design, logic, sab) |
| `manifest.webmanifest` | App ka naam, rang, icon: isi se "Install" mumkin hota hai |
| `sw.js` | Bina internet ke app kholne ke liye |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | App icons |

## Live karna (GitHub Pages)

1. Saari files repo ke **root** mein rakho.
2. Settings, Pages, "Deploy from a branch", `main` aur `/ (root)`, Save.
3. Link phone par kholo. Android Chrome mein "Install karo" aayega, iPhone par Share, phir "Add to Home Screen".

## Update karna

1. `index.html` badlo.
2. `sw.js` mein `VERSION` badlo (`apna-locker-v1` se `apna-locker-v2`), warna purani copy chalti rahegi.

## Scan, PDF aur Bhejna

Naya kaagaz jodte waqt "Camera se scan karo" se page khicho (kaala-safed saaf filter ke saath). Save ke baad har kaagaz par "PDF bhejo" dabao: WhatsApp/Gmail jaisa share menu khulega. Computer par PDF download hoti hai. Ye sab phone ke andar hota hai, koi server nahi.

## Google Drive backup (optional)

User chahe to "Drive par save karo" se apna data apne hi Google Drive me rakh sakta hai (sirf `drive.file` permission, app ki banayi file tak). Data seedha phone se Drive me jaata hai, developer ko nahi dikhta. Chalane ke liye `index.html` me `GOOGLE_CLIENT_ID` bharo: Google Cloud Console me OAuth Client ID (Web) banao, Authorized JavaScript origins me apna GitHub Pages link (jaise `https://naam.github.io`) daalo. Client ID secret nahi hota, repo me rakhna theek hai.

## Data kahan rehta hai

Abhi sab kuch (photo aur jaankari) har user ke apne browser (IndexedDB) mein rehta hai, kisi server par nahi. Phone badalne ya browser ka data saaf karne par chala jaata hai. Cloud backup aur login agla kadam hai.

**Is repo mein kabhi koi secret key ya password mat daalna.**

## Aage

- Cloud login aur encrypted backup (Supabase ya Firebase)
- Play Store par daalna: [PWABuilder](https://www.pwabuilder.com) se Android package banta hai (developer fee ek baar ka $25)
