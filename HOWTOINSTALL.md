# 🛠️ HOW TO INSTALL — Multi Platform

Panduan instalasi bot ini di berbagai platform.

---

## 🐧 Step-by-Step Instalasi di VPS (Ubuntu/Debian)

Panduan lengkap dari awal sampai bot jalan 24/7 di VPS.

### 1. Connect ke VPS

```bash
ssh root@ip_vps_kamu
# atau pake user lain:
ssh user@ip_vps_kamu
```

### 2. Update Sistem

```bash
sudo apt update && sudo apt upgrade -y
```

### 3. Install Node.js 22 LTS

```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
node -v   # harus output v22.x.x
npm -v
```

### 4. Install Git & ZIP (kalau belum ada)

```bash
sudo apt install -y git unzip zip
```

### 5. Upload / Download Script Bot

**Opsi A — Upload dari lokal ke VPS (pakai SCP):**
```bash
# Dari terminal lokal kamu (bukan VPS):
scp -r /path/ke/folder/bot root@ip_vps_kamu:/root/bot
```

**Opsi B — Clone dari GitHub (kalau di repo):**
```bash
git clone https://github.com/username/repo.git bot
```

**Opsi C — Upload file ZIP via FTP/SFTP:**
- Pakai WinSCP / FileZilla
- Upload file `.zip` ke VPS
- Extract: `unzip namafile.zip -d bot`

### 6. Masuk Folder & Install Dependencies

```bash
cd bot
npm install
```

Proses ini 1-3 menit. Kalau ada warning abaikan, selama tidak ada `ERR!` atau `failed`.

### 7. Copy & Edit Konfigurasi .env

```bash
cp .env.example .env
nano .env
```

Isi file `.env` pake data kamu:
- **BOT_TOKEN** — dari [@BotFather](https://t.me/BotFather)
- **DEVELOPER_ID** — ID Telegram kamu (cek ke [@userinfobot](https://t.me/userinfobot))
- **EMAIL_USER / EMAIL_PASS** — Gmail + App Password
- **REQUIRED_CHANNEL_*** — channel Telegram kamu
- **LOG_CHANNEL_ID** — channel buat log
- **SAWERIA_USERNAME** — username Saweria (opsional)

> 💡 **Simpan:** `Ctrl+X` → `Y` → `Enter` (nano)

### 8. Jalankan & Pastikan Berfungsi

```bash
npm start
```

Kalau ada error, cek pesannya dan perbaiki `.env`. Stop dengan `Ctrl+C`.

### 9. Jalankan 24/7 dengan PM2

```bash
npm install -g pm2
pm2 start index.js --name bot
pm2 startup
pm2 save
```

- **Cek status:** `pm2 status`
- **Lihat log:** `pm2 logs bot`
- **Restart:** `pm2 restart bot`
- **Stop:** `pm2 stop bot`

### 10. Auto-Restart Saat Reboot (Udah Otomatis)

`pm2 startup` di langkah 9 udah bikin bot jalan otomatis tiap VPS restart.  
Verifikasi: `pm2 startup` → output harus `[PM2] Init System found: systemd`

### 11. Update Script di Masa Depan

```bash
cd ~/bot
pm2 stop bot

# Kalau pake git:
git pull

# Kalau upload manual:
# Upload ulang file, extract, timpa folder

npm install        # kalau ada module baru
pm2 start bot      # jalanin ulang
```

---

## ✅ Persyaratan

| Komponen | Minimal |
|----------|---------|
| **Node.js** | 18+ (LTS) |
| **RAM** | 512 MB |
| **Storage** | 250 MB |
| **Koneksi** | Internet stabil |

---

## 📦 Install Node.js

<details>
<summary><b>🐧 Linux (Ubuntu/Debian)</b></summary>

```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs
node -v   # harus >= v18
npm -v
```
</details>

<details>
<summary><b>🪟 Windows</b></summary>

1. Download **Node.js LTS** di https://nodejs.org
2. Jalankan installer (klik Next sampai selesai)
3. Buka **Command Prompt / PowerShell**, verifikasi:
```bash
node -v
npm -v
```
</details>

<details>
<summary><b>🍎 macOS</b></summary>

```bash
# Via Homebrew (https://brew.sh)
brew install node
node -v
npm -v
```
</details>

<details>
<summary><b>📱 Termux (Android)</b></summary>

```bash
pkg update && pkg upgrade -y
pkg install nodejs -y
node -v
npm -v
```
</details>

---

## 📥 Install Bot

```bash
# 1. Ekstrak / clone script ke folder tujuan
# 2. Masuk ke folder bot
cd /path/ke/folder/bot

# 3. Install dependencies
npm install

# 4. Copy & edit konfigurasi
cp .env.example .env
nano .env   # atau notepad .env (Windows)

# 5. Jalankan
npm start
```

> 💡 **Cara edit .env di Windows:** `notepad .env` atau buka manual pakai Notepad.

---

## 🚀 Jalankan di Background

<details>
<summary><b>🐧 Linux (VPS) — pakai PM2</b></summary>

Lihat panduan lengkap di bagian **[Step-by-Step Instalasi di VPS](#-step-by-step-instalasi-di-vps-ubuntudebian)** di atas — mulai dari connect SSH sampai bot jalan 24/7.

```bash
# Intinya:
pm2 start index.js --name bot
pm2 startup
pm2 save
```
</details>

<details>
<summary><b>🪟 Windows</b></summary>

- Buka **Command Prompt / PowerShell** di folder bot
- Jalankan `npm start`
- Biarkan terminal tetap terbuka
- Atau gunakan **PM2** via `npm install -g pm2`
</details>

<details>
<summary><b>📱 Termux</b></summary>

```bash
npm install -g pm2
pm2 start index.js --name bot
# Pastikan Termux tetap jalan (jangan di-swipe)
# Gunakan Termux:Boot jika perlu auto-start
```
</details>

<details>
<summary><b>🍎 macOS</b></summary>

- Buka Terminal di folder bot
- Jalankan `npm start`
- Atau pakai PM2 seperti Linux
</details>

---

## 📝 Konfigurasi .env

Semua pengaturan ada di file `.env`. Isi sesuai kebutuhan kamu — variable yang tidak dipakai bisa dikomen dengan `#` di depannya.

Lihat file `.env.example` untuk daftar lengkap variable yang tersedia beserta penjelasannya.

---

## ⚠️ Troubleshooting Singkat

| Masalah | Solusi |
|---------|--------|
| `Cannot find module` | `npm install` |
| `BOT_TOKEN` error | Cek isi `.env` |
| Port dipakai | Matikan proses bot lama |
| Error aneh | `rm -rf node_modules && npm install` |

---

<p align="center"><strong>© 2024-2026 DikaCode</strong></p>
