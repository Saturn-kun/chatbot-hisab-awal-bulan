
# Chatbot Hisab Awal Bulan Kamariah Metode Ad-Durr Al-Anīq

> Repositori kode sumber untuk skripsi **"Pengembangan Sistem Chatbot Hisab Awal Bulan Kamariah Metode Ad-Durr Al-Anīq Berbasis Artificial Intelligence dengan Integrasi Multi-Platform (Web dan Instagram)"**

**Penulis:** M. Daviq Nuruzzuhal (NIM 2202046075)  
**Program Studi:** Ilmu Falak, Fakultas Syari'ah dan Hukum  
**Universitas:** UIN Walisongo Semarang  
**Tahun:** 2026

---

## Deskripsi

Sistem chatbot berbasis AI yang mampu melakukan perhitungan hisab awal bulan Kamariah menggunakan metode kitab *Ad-Durr Al-Anīq* karya KH. Ahmad Ghozali Muhammad Fathullah. Sistem ini terintegrasi pada dua platform: website dan Instagram Direct Message.

### Fitur Utama
- **Perhitungan Hisab Awal Bulan** — implementasi lengkap algoritma kitab Ad-Durr Al-Anīq dalam JavaScript
- **Chatbot AI** — berbasis LLM (Groq AI) yang dapat memahami pertanyaan dalam bahasa natural
- **Knowledge Base RAG** — 365+ istilah falakiyyah dari Kamus Ilmu Falak (Muhyiddin Khazin)
- **Kalkulator Hisab Manual** — mode input manual langsung di browser tanpa perlu AI
- **Integrasi Multi-Platform** — web dan Instagram DM melalui workflow n8n

## Struktur Repositori

```
├── hisab-engine/
│   └── hisab_engine.js          # Kode hisab engine (JavaScript, 485 baris)
│                                  Berisi lookup table dan seluruh algoritma
│                                  perhitungan kitab Ad-Durr Al-Aniq
│
├── web/
│   └── index.html               # Antarmuka web lengkap (HTML + CSS + JS)
│                                  Chatbot AI + Kalkulator Hisab Manual
│
├── system-message/
│   ├── web_chatbot.txt           # System message untuk chatbot web
│   └── instagram_bot.txt         # System message untuk chatbot Instagram
│
├── data/
│   └── data_prariset.csv         # Data survei pra-riset (52 responden)
│
└── docs/
    ├── arsitektur_sistem.html    # Diagram arsitektur sistem
    └── alur_integrasi.html       # Diagram alur integrasi multi-platform
```

## Arsitektur Sistem

Sistem terdiri dari empat komponen utama yang diorkestrasi melalui workflow n8n:

1. **Hisab Engine** — modul perhitungan yang mengimplementasikan seluruh algoritma kitab Ad-Durr Al-Anīq, meliputi tabel data astronomi (*lookup table*), formula koreksi (*ta'dil*), dan rumus penentuan data hilal
2. **AI Agent** — koordinator berbasis LLM Groq AI yang memproses pertanyaan pengguna dan memanggil tools yang sesuai
3. **Knowledge Base RAG** — basis pengetahuan 365+ istilah falakiyyah yang disimpan dalam vector database Supabase (pgvector)
4. **Integrasi Multi-Platform** — Instagram sebagai *discovery channel* utama yang mereferensikan pengguna ke website untuk fitur lengkap

## Teknologi yang Digunakan

| Komponen | Teknologi |
|----------|-----------|
| Workflow Orchestrator | n8n |
| LLM | Groq AI |
| Vector Database | Supabase (pgvector) |
| Bahasa Pemrograman | JavaScript |
| Hosting Web | GitHub Pages |
| Instagram API | Instagram Graph API + Webhook |

## Akurasi

Hasil uji akurasi menunjukkan tingkat akurasi **100%** terhadap aplikasi pembanding (aplikasi hisab Ad-Durr Al-Anīq karya Ali Mustofa). Pengujian dilakukan pada 12 sampel bulan Hijriah (1446 H dan 1447 H) dengan total 156 parameter yang seluruhnya menghasilkan nilai identik tanpa selisih.

## Demo

- **Website:** [saturn-kun.github.io/hisab-falak](https://saturn-kun.github.io/hisab-falak)
- **Instagram:** [@banghisab](https://instagram.com/banghisab)

## Referensi Utama

- Ahmad Ghozali Muhammad Fathullah, *Ad-Durr Al-Anīq fī Bayān al-Mazāhib al-Hisab wa al-Tauqīq* (Madura: Lafal, 2016)
- Muhyiddin Khazin, *Kamus Ilmu Falak* (Yogyakarta: Buana Pustaka, 2005)
- Roger S. Pressman dan Bruce R. Maxim, *Software Engineering: A Practitioner's Approach*, edisi 9 (New York: McGraw-Hill Education, 2020)

## Lisensi

Repositori ini merupakan bagian dari tugas akhir (skripsi) dan ditujukan untuk keperluan akademis.

---

*Skripsi ini disusun sebagai syarat memperoleh gelar Sarjana Hukum (S.H.) pada Program Studi Ilmu Falak, Fakultas Syari'ah dan Hukum, UIN Walisongo Semarang.*
