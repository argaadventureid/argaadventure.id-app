# Kerangka awal Arga 2.0

File `index.html` adalah halaman awal login Google untuk aplikasi internal Arga.

## Yang perlu diisi

1. Di Firebase Console, buka **Project settings** (ikon roda gigi) → **Your apps** → aplikasi web **Arga Internal App**.
2. Salin nilai `apiKey` dan `appId` dari konfigurasi aplikasi web ke placeholder `ISI_API_KEY` dan `ISI_APP_ID` di `index.html`.
3. Nilai konfigurasi web Firebase memang digunakan di browser. Jangan masukkan password, private key, token, atau file service account ke halaman ini.

## Cara memasukkan file ke GitHub

1. Buka repositori `argaadventureid/argaadventure.id-app`.
2. Pilih **Add file** → **Upload files**.
3. Unggah `index.html` dan `PETUNJUK.md`.
4. Klik **Commit changes** untuk menyimpan file.

## Batas keamanan saat ini

Halaman ini hanya melakukan login Google melalui Firebase. Ia sengaja belum memberikan akses ke data internal. `ACCESS_CHECK_URL` dibiarkan kosong sampai backend memverifikasi Firebase ID token, mengecek whitelist pengguna aktif, dan mengembalikan role. Jangan sambungkan Google Sheets atau data operasional sebelum pemeriksaan backend itu tersedia.

Setelah backend siap, masukkan URL endpoint pemeriksaan akses ke `ACCESS_CHECK_URL`. Backend wajib memverifikasi token di server; jangan mempercayai email atau role yang dikirim langsung oleh browser.

## Domain

Setelah aplikasi dipublikasikan, tambahkan hostname yang benar-benar digunakan ke **Firebase Authentication → Settings → Authorized domains**. Untuk domain khusus, tambahkan `app.argaadventure.id` setelah DNS dan GitHub Pages sudah disiapkan.
