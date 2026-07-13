<div align="center">
  <img src="https://files.catbox.moe/ecvmlf.jpg" alt="Logo" width="120" height="120" style="border-radius: 20px;" />

  <h1 align="center">🤖 WhatsApp Recovery Bot</h1>

  <p align="center">
    <strong>Telegram Bot untuk Recovery &amp; Verifikasi Akun WhatsApp</strong>
    <br />
    Kirim appeal massal, fix code OTP, cek nomor WA, dan kelola akun — langsung dari Telegram!
    <br />
    <br />
    <a href="#-features">📋 Features</a>
    ·
    <a href="#-setup">⚙️ Setup</a>
    ·
    <a href="#-usage">🚀 Usage</a>
    ·
    <a href="#-admin-panel">🛡️ Admin</a>
    ·
    <a href="#-tech-stack">🧱 Tech Stack</a>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/WhatsApp-Baileys-25D366?logo=whatsapp&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Telegram-Bot_API-2CA5E0?logo=telegram&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Email-SMTP-EA4335?logo=gmail&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Payment-QRIS-FF5722?logo=react&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Database-Supabase-3ECF8E?logo=supabase&amp;logoColor=white" />
  </p>
</div>

---

## 📋 Table of Contents

- [✨ Features](#-features)
- [⚙️ Setup](#️-setup)
- [🚀 Usage](#-usage)
- [🎁 Referral Program](#-referral-program)
- [👑 VIP Premium](#-vip-premium)
- [🛡️ Admin Panel](#️-admin-panel)
- [📁 Project Structure](#-project-structure)
- [🧱 Tech Stack](#-tech-stack)
- [☁️ Cloud Backup (Supabase)](#️-cloud-backup-supabase)
- [🔒 Security](#-security)
- [📄 License](#-license)

---

## ✨ Features

### 📧 Email Services
| Fitur | Deskripsi |
|-------|-----------|
| **Fix Login Unavailable** | Kirim email appeal ke 60+ alamat support WhatsApp untuk error &quot;Login Unavailable&quot; |
| **Fix Code 1 Jam** | Atasi error &quot;Try Again in 1 Hour&quot; — kirim laporan OTP tidak terkirim |
| **Request SMS Code** | Minta WhatsApp kirimkan SMS OTP (bukan Call) untuk verifikasi |

Setiap email dikirim dengan **staggered delivery** (delay acak antar email), **CC rotation**, dan **template bervariasi** (5+ template berbeda) agar terlihat natural &amp; tidak terdeteksi spam.

### 📱 WhatsApp Checker
| Fitur | Deskripsi |
|-------|-----------|
| **Pair Device** | Hubungkan nomor WhatsApp via **Pairing Code** (bukan QR) |
| **Cek Nomor** | Periksa apakah nomor terdaftar di WhatsApp + lihat Bio |
| **Batch Check** | Upload file `.txt` — periksa ratusan nomor sekaligus |

Auto-reconnect saat 515/restartRequired — pairing tetap berhasil sampai device benar-benar ter-link.

### 🎁 Referral Program
- Dapatkan **token gratis** dengan mengajak teman
- 1 referral = +1 Appeal, +1 FixCode, +1 SMS token
- Token = akses instan tanpa cooldown
- **Share Link** — bagikan referral langsung ke chat Telegram

### 👑 VIP Premium
- ✅ Akses unlimited — kirim appeal &amp; fixcode tanpa batas
- ✅ Tanpa cooldown &amp; tanpa token
- ✅ Pembayaran via **QRIS** (Saweria)
- ✅ Custom durasi (1–365 hari)
- Harga: **Rp1.000/hari**

### 💝 Donasi Email
User bisa **donasikan akun Gmail** mereka untuk jadi server pengirim tambahan. Email diverifikasi otomatis (SMTP check) sebelum ditambahkan.

### 🔐 Channel Verification
User wajib join channel Telegram tertentu sebelum bisa menggunakan bot. Verifikasi otomatis melalui tombol **VERIFY**.

---

## ⚙️ Setup

### Prerequisites
- **Node.js** 18+ (LTS recommended)
- **Telegram Bot Token** (dari [@BotFather](https://t.me/BotFather))
- **Gmail App Password** untuk server email primer
- **(Optional)** Akun [Supabase](https://supabase.com) Free untuk cloud backup
- **(Optional)** Username [Saweria](https://saweria.co) untuk pembayaran QRIS

### 1. Clone &amp; Install

```bash
git clone https://github.com/yourusername/whatsapp-appeal-bot.git
cd whatsapp-appeal-bot
npm install
```

### 2. Konfigurasi `.env`

```bash
cp .env.example .env
# lalu edit .env sesuai kebutuhan
```

#### Required
```env
BOT_TOKEN=your_bot_token_from_botfather
DEVELOPER_ID=your_telegram_user_id
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_gmail_app_password
REQUIRED_CHANNEL_USERNAME=@channel_1
REQUIRED_CHANNEL_ID=-1001234567890
LOG_CHANNEL_ID=-1001234567890
```

#### Optional (fitur spesifik)
```env
# Channel kedua (opsional)
REQUIRED_CHANNEL2_USERNAME=@channel_2
REQUIRED_CHANNEL2_ID=-1001234567891

# Saweria untuk QRIS payment
SAWERIA_USERNAME=your_saweria_username

# Supabase untuk cloud backup
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_KEY=your_service_role_key

# Encryption key untuk password email server
ENCRYPTION_KEY=32_hex_chars

# Customization
BOT_IMAGE_URL=https://your-image-url.jpg
NODE_ENV=production
```

### 3. Dapatkan Telegram Credentials

| Item | Cara Dapat |
|------|-----------|
| **Bot Token** | Chat [@BotFather](https://t.me/BotFather) → `/newbot` |
| **User ID** | Chat [@userinfobot](https://t.me/userinfobot) → `/start` |
| **Channel/Group ID** | Forward pesan ke [@getidsbot](https://t.me/getidsbot) |
| **Gmail App Password** | `myaccount.google.com/security` → App Passwords |

### 4. Jalankan Bot

```bash
# Production
npm start

# Development (auto-restart)
npm run dev
```

---

## 🚀 Usage

### User Commands

| Command | Deskripsi |
|---------|-----------|
| `/start` | Menu utama &amp; registrasi |
| `/start ref_&lt;id&gt;` | Join via referral link (otomatis) |
| `/vip` | Info &amp; pembelian VIP premium |

### Tombol Menu

```
📧 FIX LOGIN UNAVAILABLE
    → Masukkan nomor HP (62xx)
    → Pilih server email
    → Email appeal terkirim ke 60+ alamat support WA

⏱ FIX CODE 1 JAM
    → Masukkan nomor HP (62xx)
    → Pilih server email
    → Laporan OTP error terkirim

📨 FIX NO OPSI SMS
    → Masukkan nomor HP (62xx)
    → Minta WhatsApp kirim SMS code

📱 BIO WA CHECKER
    → Pair device → Cek nomor / Upload .txt
```

### Flow Appeal
```
User klik "📧 FIX LOGIN UNAVAILABLE"
    ↓
Cek membership channel (wajib join)
    ↓
Cek cooldown / referral token
    ↓
Masukkan nomor HP (628xx)
    ↓
Pilih server email (server 1, 2, atau custom)
    ↓
✅ Email terkirim ke support WhatsApp
    ↓
Cooldown 1 jam (free user) / token dipakai
```

---

## 🎁 Referral Program

Dapatkan **token gratis** dengan mengajak teman menggunakan link referral unikmu.

```
🎁 PROGRAM REFERRAL

📊 Saldo Token:
  📧 Appeal: 2 token
  ⏱ FixCode: 2 token
  📨 SMS: 0 token

🔗 Link Kamu:
https://t.me/yourbot?start=ref_123456

💡 Cara kerja:
  1. Bagikan link ke teman
  2. Teman klik link & JOIN semua channel
  3. Teman tekan VERIFY
  4. Kamu dapat +1 Appeal, FixCode & SMS
```

**Token** digunakan untuk akses instan tanpa cooldown. Cocok untuk user free yang ingin kirim ulang tanpa menunggu.

---

## 👑 VIP Premium

Akses unlimited ke semua fitur dengan pembayaran QRIS via Saweria.

| Durasi | Harga | Pembayaran |
|--------|-------|------------|
| 1 hari | Rp1.000 | ✅ QRIS |
| 2 hari | Rp2.000 | ✅ QRIS |
| 3 hari | Rp3.000 | ✅ QRIS |
| 7 hari | Rp7.000 | ✅ QRIS |
| 30 hari | Rp30.000 | ✅ QRIS |
| Custom | Rp1.000/hari | ✅ QRIS |

Pembayaran diproses otomatis — setelah lunas, VIP langsung aktif. Polling status 5 detik dengan countdown.

---

## 🛡️ Admin Panel

Akses: `⚙️ ADMIN` (khusus owner/developer)

| Menu | Fungsi |
|------|--------|
| **👑 ADD PREMIUM** | Beri akses premium ke user |
| **👑 REM PREMIUM** | Cabut akses premium |
| **📋 LIST PREMIUM** | Lihat semua user premium |
| **👥 ALL USERS** | Statistik &amp; daftar user |
| **📢 BROADCAST** | Kirim pesan ke semua user |
| **💝 ADD EMAIL** | Tambah server email donasi |
| **📋 LIST EMAIL** | Lihat server email aktif |
| **🗑 DELETE EMAIL** | Hapus server email |
| **📱 LIST DEVICE** | Lihat device WA terpair |
| **🗑 HAPUS DEVICE** | Hapus device WA |
| **👑 ADD/REMOVE OWNER** | Kelola owner (dev-only) |

Admin panel menampilkan dashboard:
```
╔ ⭐ Developer
║ 👥 Users: 150
║ 👑 Premium: 5 (3 permanen, 2 terbatas)
║ 📱 Devices: 2/3 online
╚ 💝 Donasi: 8 server
```

---

## 📁 Project Structure

```
📦 whatsapp-appeal-bot/
├── 📄 index.js                 # Entry point + graceful shutdown
├── 📄 .env                     # Environment variables
├── 📄 .env.example             # Template env
├── 📄 package.json             # Dependencies
├── 📄 supabase-migration.sql   # SQL untuk Supabase tables
│
├── 📁 src/
│   ├── 📄 bot.js               # Telegram bot handlers (main logic)
│   ├── 📄 ui.js                # UI helpers — keyboard builder, sendMessage, etc.
│   ├── 📄 config.js            # Config — env vars, templates, email lists
│   ├── 📄 db.js                # Database layer — JSON file store accessors
│   ├── 📄 store.js             # JSON file store class (atomic saves)
│   ├── 📄 state.js             # User state machine + rate limiter + cooldown
│   ├── 📄 email.js             # Email delivery — sendAppeal, sendFixCode, sendSmsRequest
│   ├── 📄 wa.js                # WhatsApp Multi-Device — pair, QR, check numbers
│   ├── 📄 wa-api.js            # WhatsApp API helpers
│   ├── 📄 saweria.js           # Saweria QRIS payment integration
│   └── 📄 cloud-db.js          # Supabase cloud backup (fire-and-forget)
│
├── 📁 sessions/                # WhatsApp session data (auto-generated)
│
├── 📄 users.json               # User database (auto-generated)
├── 📄 premium.json             # Premium members (auto-generated)
├── 📄 owners.json              # Bot owners (auto-generated)
├── 📄 devices.json             # WA devices (auto-generated)
├── 📄 referrals.json           # Referral balances (auto-generated)
├── 📄 donated_servers.json     # Donated email servers (auto-generated)
└── 📄 rate-limit-state.json    # Rate limit persistence (auto-generated)
```

---

## 🧱 Tech Stack

| Technology | Purpose |
|-----------|---------|
| **Node.js** | Runtime |
| **node-telegram-bot-api** | Telegram Bot API wrapper |
| **@whiskeysockets/baileys** | WhatsApp Multi-Device client |
| **nodemailer** | Email delivery via Gmail SMTP |
| **@supabase/supabase-js** | Cloud database backup |
| **axios + cheerio** | Saweria payment scraping |
| **pino + pino-pretty** | Logging |

### API Integration

- **Telegram Bot API** — semua request via `fetch()` langsung (tanpa library abstraksi) untuk dukungan penuh inline keyboard style
- **WhatsApp Web API** — Baileys MD (Multi-Device) protocol
- **Gmail SMTP** — email delivery dengan staggered delay anti-spam
- **Saweria** — QRIS payment via scraping + backend API
- **Supabase REST API** — cloud backup via service_role key

---

## ☁️ Cloud Backup (Supabase)

Bot otomatis mem-backup semua data ke **Supabase Free Tier** setiap kali ada perubahan.

### Fitur
- ✅ Fire-and-forget — tidak blokir response bot
- ✅ Setiap `save()` lokal → langsung sync ke cloud
- ✅ Full sync saat startup + periodic tiap 5 menit
- ✅ Non-blocking — bot tetap jalan walau Supabase error
- ✅ Encrypted password untuk email server

### Database Tables

| Table | Primary Key | Isi |
|-------|-------------|-----|
| `users` | `id` (BIGINT) | Data user Telegram |
| `owners` | `id` (BIGINT) | Bot admin |
| `premium` | `id` (BIGINT) | VIP members |
| `referrals` | `user_id` (BIGINT) | Token balances |
| `devices` | `chat_id` (BIGINT) | WA sessions |
| `donated_servers` | `id` (SERIAL) | Email servers (encrypted) |

### Setup Backup

Jalankan `supabase-migration.sql` di Supabase SQL Editor, lalu isi `.env`:
```env
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_KEY=your_service_role_key
```

---

## 🔒 Security

- **App Passwords** — tidak pernah menyimpan password Gmail asli, hanya App Password 16 karakter
- **Encryption** — password email server di-enkripsi (AES-256-CBC) sebelum disimpan
- **Channel Gate** — user wajib join channel sebelum akses bot
- **Rate Limiting** — sliding window (3 request/menit) + cooldown 1 jam (free user)
- **Privacy** — nomor HP &amp; email user dihapus dari chat setelah diproses

---

## ❓ Troubleshooting

| Problem | Solution |
|---------|----------|
| Bot tidak merespon | Pastikan `BOT_TOKEN` benar, restart bot |
| Pairing WA gagal | Coba ulang, pastikan nomor benar (62xx) |
| Email tidak terkirim | Cek App Password, coba custom email |
| QRIS tidak muncul | Pastikan `SAWERIA_USERNAME` benar |
| Supabase sync error | Cek `SUPABASE_URL` &amp; `SUPABASE_SERVICE_KEY` |
| &quot;Login Unavailable&quot; | Itu yang mau di-fix — kirim appeal! |

---

## 📄 License

Distributed under the MIT License.

---

<div align="center">
  <p>Made with ❤️ for the WhatsApp recovery community</p>
  <p>
    <a href="https://t.me/yourchannel">📢 Channel</a>
    ·
    <a href="https://github.com/yourusername/whatsapp-appeal-bot/issues">🐛 Report Bug</a>
    ·
    <a href="https://github.com/yourusername/whatsapp-appeal-bot/issues">✨ Request Feature</a>
  </p>
</div>
