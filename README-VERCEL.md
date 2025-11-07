Panduan deploy ke Vercel (SPA dari folder `dist`)

Persyaratan singkat:
- Akun Vercel (https://vercel.com)
- Node.js + npm terpasang (kamu sudah menjalankan `node server.js`)

1) Opsi cepat: deploy via Vercel CLI (direkomendasikan)

Buka PowerShell di folder project (`C:\Users\user\Desktop\github`) lalu jalankan:

```powershell
npm install -g vercel
vercel login
# setelah login berhasil, jalankan:
vercel --prod
```

Catatan:
- Vercel akan mendeteksi `vercel.json` dan mengunggah `dist` sebagai situs statis.
- Kami sudah menambahkan `vercel.json` yang menggunakan `@vercel/static` dan route fallback ke `index.html` untuk React Router.

2) Opsi Git (CI):
- Push repository ini ke GitHub/GitLab dan hubungkan repo ke Vercel lewat dashboard Vercel.
- Atur build output directory ke `dist` bila perlu (biasanya tidak dibutuhkan karena `vercel.json` sudah mengatur build).

Jika kamu memilih CLI dan ingin, saya bisa membantumu menjalankan `vercel --prod` dari sini—tapi kamu harus melakukan `vercel login` secara interaktif karena butuh autentikasi.

Masalah umum & troubleshooting:
- Jika `dist` belum berisi file build, jalankan build dari project React/Vue/Angular sebelum deploy.
- Jika kamu memerlukan behaviour server (Express), Vercel tidak menjalankan long-running servers. Untuk API, pindahkan ke serverless (folder `api/`) atau gunakan platform lain (Heroku, Render, Railway).

Butuh saya coba jalankan deploy sekarang? Jika iya, beri izin untuk menginstal CLI dan ingat kamu harus melakukan login interaktif saat diminta.
