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
    <a href="#-quick-start">⚙️ Quick Start</a>
    ·
    <a href="#-pricing">💰 Pricing</a>
    ·
    <a href="#-tech-stack">🧱 Tech Stack</a>
    ·
    <a href="#-admin-panel">🛡️ Admin</a>
    <br />
    <br />
    <a href="https://t.me/dikaacode">
      <img src="https://img.shields.io/badge/BUY-Rp100.000-FF5733?logo=telegram&amp;logoColor=white&amp;style=for-the-badge" alt="Buy Rp100.000" />
    </a>
    <a href="https://t.me/dikaacode">
      <img src="https://img.shields.io/badge/Contact-@dikaacode-0088CC?logo=telegram&amp;logoColor=white&amp;style=for-the-badge" alt="Contact @dikaacode" />
    </a>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/WhatsApp-Baileys-25D366?logo=whatsapp&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Telegram-Bot_API-2CA5E0?logo=telegram&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Email-SMTP-EA4335?logo=gmail&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Payment-QRIS-FF5722?logo=react&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Database-Supabase-3ECF8E?logo=supabase&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Database-MongoDB-47A248?logo=mongodb&amp;logoColor=white" />
  </p>
</div>

---

## ✨ Features

### 📧 Email Services
| Fitur | Deskripsi |
|-------|-----------|
| **Fix Login Unavailable** | Kirim email appeal ke 60+ alamat support WhatsApp |
| **Fix Code 1 Jam** | Atasi error "Try Again in 1 Hour" — kirim laporan OTP tidak terkirim |
| **Request SMS Code** | Minta WhatsApp kirimkan SMS OTP (bukan Call) untuk verifikasi |

Staggered delivery + CC rotation + 5+ template variasi agar terhindar dari spam detection.

### 📱 WhatsApp Checker
| Fitur | Deskripsi |
|-------|-----------|
| **Pair Device** | Hubungkan nomor WhatsApp via Pairing Code (bukan QR) |
| **Cek Nomor** | Periksa apakah nomor terdaftar di WhatsApp + lihat Bio |
| **Batch Check** | Upload file `.txt` — periksa ratusan nomor sekaligus |

### 🎁 Referral Program
- Dapatkan **token gratis** dengan mengajak teman
- 1 referral = +1 Appeal, +1 FixCode, +1 SMS token
- Token = akses instan tanpa cooldown

### 👑 VIP Premium
- ✅ Akses unlimited tanpa batas, cooldown, & token
- ✅ Pembayaran via **QRIS** otomatis
- ✅ Custom durasi 1–365 hari atau ♾️ permanen

### 💝 Donasi Email
Donasikan akun Gmail untuk jadi server pengirim tambahan. Diverifikasi otomatis via SMTP.

### 🔐 Channel Verification
User wajib join channel Telegram tertentu sebelum bisa pakai bot. Verifikasi otomatis via tombol **VERIFY**.

---

## 💰 Pricing

| Item | Harga |
|------|-------|
| **Script Full** | **Rp100.000** |

Free update seumur hidup setelah beli.

**Contact:** [@DikaCode](https://t.me/DikaCode)

---

## ⚙️ Quick Start

```bash
npm install     # Install dependencies
npm start       # Start bot
```

> 💡 Lihat [HOWTOINSTALL.md](HOWTOINSTALL.md) untuk panduan instalasi lengkap di berbagai platform (VPS, Windows, macOS, Termux).

### Requirements
- **Node.js** 18+ (LTS)
- **Telegram Bot Token** dari [@BotFather](https://t.me/BotFather)
- **Gmail + App Password** untuk server email

---

## 🛡️ Admin Panel

Akses: `⚙️ ADMIN` (khusus owner/developer)

| Menu | Fungsi |
|------|--------|
| **👑 ADD PREMIUM** | Beri akses premium ke user |
| **👑 REM PREMIUM** | Cabut akses premium |
| **📋 LIST PREMIUM** | Lihat semua user premium |
| **👥 ALL USERS** | Statistik & daftar user |
| **📢 BROADCAST** | Kirim pesan ke semua user |
| **💝 ADD EMAIL** | Tambah server email donasi |
| **📋 LIST EMAIL** | Lihat server email aktif |
| **🗑 DELETE EMAIL** | Hapus server email |
| **📱 LIST DEVICE** | Lihat device WA terpair |
| **🗑 HAPUS DEVICE** | Hapus device WA |
| **👑 ADD/REMOVE OWNER** | Kelola owner (dev-only) |

---

## 🧱 Tech Stack

| Technology | Purpose |
|-----------|---------|
| **Node.js** | Runtime |
| **node-telegram-bot-api** | Telegram Bot API wrapper |
| **@whiskeysockets/baileys** | WhatsApp Multi-Device client |
| **nodemailer** | Email delivery via Gmail SMTP |
| **@supabase/supabase-js** | Cloud backup (PostgreSQL) |
| **mongodb** | Cloud backup (MongoDB Atlas) |
| **pino + pino-pretty** | Logging |

### API Integration
- **Telegram Bot API** — semua request via `fetch()` langsung
- **WhatsApp Web API** — Baileys MD (Multi-Device) protocol
- **Gmail SMTP** — email delivery dengan staggered delay anti-spam
- **Supabase REST API** — cloud backup via service_role key
- **MongoDB Atlas** — cloud backup NoSQL via native driver

---

## 🔒 Security

- **App Passwords** — tidak pernah menyimpan password Gmail asli
- **Encryption** — password email server di-enkripsi AES-256-CBC
- **Channel Gate** — user wajib join channel sebelum akses bot
- **Rate Limiting** — sliding window 3 request/menit + cooldown 1 jam
- **Privacy** — nomor HP & email user dihapus dari chat setelah diproses

---

## 📄 License

Distributed under the MIT License.

---

<div align="center">
  <p>Made with ❤️ for the WhatsApp recovery community</p>
  <p>
    <a href="https://t.me/execuidorbaru">📢 Channel</a>
    ·
    <a href="https://t.me/dikaacode">🐛 Report Bug</a>
    ·
    <a href="https://t.me/dikaacode">✨ Request Feature</a>
  </p>
</div>
