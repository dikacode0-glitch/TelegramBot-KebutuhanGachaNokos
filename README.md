
<div align="center">

<!-- HERO LOGO -->
<img src="https://files.catbox.moe/ecvmlf.jpg" alt="Logo WhatsApp Recovery" width="140" height="140" style="border-radius: 28px; box-shadow: 0px 8px 24px rgba(37, 211, 102, 0.2); border: 2px solid #25D366;" />

# 🌌 WHATSAPP RECOVERY BOT
### ⚡ *The Ultimate Digital Assistant for WhatsApp Account Verification & Recovery* ⚡

<p align="center">
  <a href="#-key-features">✨ Fitur Utama</a> •
  <a href="#-system-architecture">⚙️ Arsitektur</a> •
  <a href="#-quick-start">🚀 Panduan Cepat</a> •
  <a href="#-pricing">💎 Lisensi</a> •
  <a href="#-security">🛡️ Keamanan</a>
</p>

<!-- PREMIUM BADGES -->
<p align="center">
  <a href="https://t.me/dikaacode">
    <img src="https://img.shields.io/badge/⚡_PREMIUM_ACCESS-Rp100.000-0088CC?style=for-the-badge&logo=telegram&logoColor=white" alt="Beli Bot" />
  </a>
  <a href="https://t.me/dikaacode">
    <img src="https://img.shields.io/badge/📥_DEVELOPER-@DikaaCode-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="Developer" />
  </a>
</p>

<!-- TECH BADGES -->
<p align="center">
  <img src="https://img.shields.io/badge/Runtime-Node.js_18%2B-339933?style=flat-square&logo=node.js&logoColor=white" />
  <img src="https://img.shields.io/badge/Engine-Baileys_MD-25D366?style=flat-square&logo=whatsapp&logoColor=white" />
  <img src="https://img.shields.io/badge/Interface-Telegram_API-2CA5E0?style=flat-square&logo=telegram&logoColor=white" />
  <img src="https://img.shields.io/badge/SMTP-Nodemailer_Secure-EA4335?style=flat-square&logo=gmail&logoColor=white" />
  <img src="https://img.shields.io/badge/Database-Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white" />
  <img src="https://img.shields.io/badge/Database-MongoDB_Atlas-47A248?style=flat-square&logo=mongodb&logoColor=white" />
</p>

</div>

---

## 🌌 SYSTEM ARCHITECTURE (3D FLOW)

graph TD
    User([👤 User / Client]) -->|Kirim Perintah / Data| Telegram[🤖 Telegram Bot API]
    Telegram -->|Proses Input| Core[💻 Node.js Engine]
    Core -->|1. Request OTP / Pairing| WA[💬 WhatsApp Web API / Baileys]
    Core -->|2. Kirim Appeal / Bypass| SMTP[📧 Gmail SMTP Servers]
    Core -->|3. Validasi & Simpan| DB[(☁️ Supabase / MongoDB)]
    
    style User fill:#1F2937,stroke:#3B82F6,stroke-width:2px;
    style Telegram fill:#1E3A8A,stroke:#2563EB,stroke-width:2px;
    style Core fill:#111827,stroke:#10B981,stroke-width:3px;
    style WA fill:#064E3B,stroke:#059669,stroke-width:2px;
    style SMTP fill:#7F1D1D,stroke:#DC2626,stroke-width:2px;
    style DB fill:#312E81,stroke:#6366F1,stroke-width:2px;

✨ KEY FEATURES

🪐 1. Layanan Email Bypass (SMTP Integration)

Sistem pengiriman banding otomatis yang cerdas dengan rotasi server terenkripsi.

  - ⚡ Fix Login Unavailable: Mengirimkan dokumen banding (appeal) secara
    simultan ke 60+ alamat email dukungan resmi WhatsApp.
  - 🕒 Fix Code 1 Jam: Mengatasi masalah penundaan kode OTP ("Try Again in 1
    Hour") dengan laporan delivery failure otomatis.
  - 📥 Request SMS Code: Memaksa sistem pengirim WhatsApp untuk mengirimkan
    verifikasi via SMS sebagai pengganti panggilan suara (Voice Call).
  - Sistem Pengiriman: Menggunakan teknologi Staggered Delivery, CC Rotation,
    dan 5+ Variasi Template Dinamis guna meminimalisir deteksi spam.

📱 2. WhatsApp Checker & Linkage

Integrasi langsung ke protokol web WhatsApp tanpa repot.

  - 🔑 Pair Device: Menghubungkan nomor WhatsApp target menggunakan Pairing Code
    langsung dari bot (tanpa perlu pemindaian QR Code).
  - 🔍 Check Number: Memeriksa status keaktifan nomor pada jaringan WhatsApp
    beserta informasi Bio terbaru secara real-time.
  - 📂 Bulk/Batch Check: Memungkinkan unggahan berkas berkstensi .txt berisi
    ratusan nomor untuk diperiksa secara massal dan instan.

🫂 3. Growth & Referral Engine

Sistem rujukan organik untuk meningkatkan interaksi pengguna di dalam komunitas
Anda.

  - Ajak Teman: Hasilkan poin/token gratis secara otomatis setiap kali pengguna
    baru mendaftar menggunakan tautan rujukan Anda.
  - Struktur Poin: 1 Referral = +1 Appeal, +1 FixCode, dan +1 SMS Token.
  - Instant Access: Token yang berhasil dikumpulkan dapat langsung digunakan
    tanpa batasan waktu tunggu (cooldown).

🛡️ CORE SECURITY PROTOCOLS

Sistem dibangun dengan fokus utama pada keamanan data sensitif pengguna.

| Sektor Keamanan            | Mekanisme Pertahanan                                                                                                        |
| :------------------------- | :-------------------------------------------------------------------------------------------------------------------------- |
| **🔑 Autentikasi Pengirim** | Menggunakan sistem *Gmail App Passwords* (mencegah penyimpanan kata sandi email asli).                                      |
| **🔐 Enkripsi Data**        | Seluruh konfigurasi kredensial SMTP dienkripsi menggunakan metode algoritma **AES-256-CBC**.                                |
| **🚪 Gerbang Komunitas**    | Fitur *Channel Gate* otomatis; mewajibkan pengguna bergabung ke kanal Telegram yang ditentukan sebelum dapat mengakses bot. |
| **⏱️ Pembatas Akses**      | Penerapan batas ketat (*Sliding Window*) maksimal 3 permintaan per menit dengan *cooldown* global selama 1 jam.             |
| **🕵️ Kebijakan Privasi**   | Penghapusan data nomor telepon serta berkas pengirim secara otomatis dari memori server setelah proses selesai.             |

💰 PRICING PLANS

┌──────────────────────────────────────────────────────────┐
│                     💎 PRICING PLAN 💎                   │
├────────────────────────────┬─────────────────────────────┤
│        PRODUCT TYPE        │            PRICE            │
├────────────────────────────┼─────────────────────────────┤
│ 🧾 Full Script Code base   │ Rp50.000                    │
│ 🔄 Lifetime Updates        │ FREE (Selamanya)            │
│ ⚡ VIP Premium Bot Access  │ Mulai Rp100.000             │
└────────────────────────────┴─────────────────────────────┘

Untuk pembelian lisensi resmi atau akses premium otomatis via QRIS: 👉 Hubungi
Developer Resmi: @DikaaCode 👈

⚙️ QUICK START

Persyaratan Minimum

  - Runtime Environment: Node.js versi 18 (LTS) atau lebih tinggi.
  - Akses Telegram: Kunci token bot yang dibuat melalui @BotFather.
  - Kredensial Server: Akun Gmail aktif yang telah mengaktifkan fitur App
    Password.

Langkah Instalasi Cepat

# 1. Kloning repositori & masuk ke direktori proyek
git clone https://github.com/dikacode0-glitch/whatsapp-recovery-bot.git
cd whatsapp-recovery-bot

# 2. Pasang modul dependensi yang diperlukan
npm install

# 3. Konfigurasi berkas lingkungan Anda
cp .env.example .env
nano .env  # Isikan Token Bot, Supabase, & MongoDB URI Anda

# 4. Jalankan aplikasi utama
npm start

💡 Panduan instalasi mendalam untuk platform VPS, Windows, macOS, maupun Termux
tersedia pada dokumen HOWTOINSTALL.md.

👑 CONTROL PANEL ADMIN (OWNER MENU)

Fitur panel kendali khusus untuk administrator utama guna mengontrol
fungsionalitas bot secara penuh.

📁 PANEL ADMINISTRASI UTAMA
├── 👑 MANAJEMEN PREMIUM
│   ├── ➕ ADD PREMIUM       --> Memberikan lisensi VIP kepada pengguna
│   ├── ➖ REM PREMIUM       --> Menarik kembali lisensi VIP
│   └── 📋 LIST PREMIUM      --> Menampilkan seluruh daftar pengguna VIP aktif
├── 📊 DATA & STATISTIK
│   ├── 👥 ALL USERS         --> Melihat statistik total pendaftar unik
│   └── 📢 BROADCAST         --> Mengirim pesan siaran massal ke seluruh pengguna
├── 📧 MANAJEMEN SMTP EMAIL
│   ├── 💝 ADD EMAIL         --> Menambahkan server SMTP email donatur baru
│   ├── 📋 LIST EMAIL        --> Melihat daftar server SMTP aktif
│   └── 🗑️ DELETE EMAIL      --> Menghapus server SMTP dari sistem
└── 📱 MANAJEMEN PERANGKAT WA
    ├── 📱 LIST DEVICE       --> Menampilkan daftar nomor WA yang terhubung
    └── 🗑️ HAPUS DEVICE      --> Memutuskan sesi tautan nomor WA tertentu

🤝 Didukung Oleh Komunitas

Dibuat dengan dedikasi penuh bagi komunitas pemulihan akun digital WhatsApp.

Kanal Telegram Situs Resmi

© 2024-2026 DikaCode — MIT License
