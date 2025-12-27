# 📍 Location Tracker - Vercel Edition

Aplikasi GPS Location Tracker yang di-deploy ke Vercel dengan Vercel KV sebagai database.

## 🚀 Cara Deploy ke Vercel

### Step 1: Siapkan Repository

1. Upload folder ini ke GitHub repository baru
2. Atau gunakan Vercel CLI

### Step 2: Setup Vercel KV (Database)

1. Buka [vercel.com](https://vercel.com) dan login
2. Pilih project kamu
3. Pergi ke **Storage** tab
4. Klik **Create Database** → pilih **KV**
5. Beri nama database (misal: `location-tracker-kv`)
6. Klik **Create**
7. Database akan otomatis terkoneksi ke project

### Step 3: Deploy

**Via Vercel Dashboard:**
1. Buka [vercel.com/new](https://vercel.com/new)
2. Import repository GitHub kamu
3. Klik **Deploy**

**Via CLI:**
```bash
npm i -g vercel
vercel login
vercel
```

### Step 4: Gunakan Aplikasi

Setelah deploy selesai:
- **Dashboard**: `https://[nama-project].vercel.app`
- **Tracker**: `https://[nama-project].vercel.app/tracker`

## 📱 Cara Penggunaan

1. Buka link **Tracker** di browser HP
2. Isi nama perangkat
3. Klik **"Mulai Tracking"**
4. Izinkan akses lokasi
5. Lihat lokasi di **Dashboard**

## 📁 Struktur File

```
location-tracker-vercel/
├── api/
│   ├── location.js         # API terima lokasi
│   └── devices/
│       ├── index.js        # API list devices
│       └── [id].js         # API device detail & delete
├── public/
│   ├── dashboard.html      # Dashboard dengan peta
│   └── tracker.html        # Halaman tracker HP
├── package.json
├── vercel.json             # Konfigurasi Vercel
└── README.md
```

## 🔌 API Endpoints

| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| POST | `/api/location` | Kirim lokasi baru |
| GET | `/api/devices` | List semua perangkat |
| GET | `/api/devices/[id]` | Detail & history device |
| DELETE | `/api/devices/[id]` | Hapus device |

## ⚠️ Catatan Penting

### Vercel KV
- Vercel KV gratis untuk hobby plan
- Data persistent dan real-time
- Tidak perlu setup server database sendiri

### HTTPS
- Vercel otomatis menyediakan HTTPS
- GPS di browser butuh HTTPS (sudah tercover)

### Limits
- Maksimal 500 lokasi per perangkat disimpan
- Data refresh setiap 5 detik di dashboard

## 🔧 Local Development

```bash
npm install
npx vercel dev
```

Ini akan menjalankan development server dengan emulasi Vercel environment.

## 💡 Tips

1. **Hemat baterai**: Gunakan interval 30-60 detik
2. **Akurasi GPS**: Buka di area terbuka untuk GPS lock lebih baik
3. **Background tracking**: HP harus tetap aktif (tidak sleep)

---

Made with ❤️ for Vercel deployment
