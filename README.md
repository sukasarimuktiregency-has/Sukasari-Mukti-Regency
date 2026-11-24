# Sukasari Mukti Regency — Website

Website statis untuk Sukasari Mukti Regency. Halaman utama tersedia di `index.html`.
Aset logo dan ikon WhatsApp pada versi ini sudah tertanam di dalam HTML, sehingga tidak
memerlukan folder aset terpisah untuk tampilan awal.

## Deploy ke GitHub

1. Ekstrak ZIP ini ke komputer.
2. Buat repository baru di GitHub, misalnya `sukasari-mukti-regency`.
3. Upload seluruh isi folder ini ke root repository (pastikan `index.html` berada di root).
4. Commit perubahan.

## Deploy ke Vercel

1. Masuk ke https://vercel.com/ lalu pilih **Add New → Project**.
2. Import repository GitHub `sukasari-mukti-regency`.
3. Untuk website ini tidak perlu Build Command maupun Output Directory khusus.
   Biarkan framework sebagai **Other** dan Root Directory sebagai `./`.
4. Klik **Deploy**.
5. Setelah deploy selesai, Vercel akan memberikan URL `.vercel.app`.
6. Untuk domain sendiri, tambahkan domain melalui **Project → Settings → Domains**.

Setiap push/commit baru ke branch produksi yang terhubung akan memicu deployment baru.

## Catatan penting sebelum dipakai sebagai website produksi

Versi ini dapat di-host sebagai website statis di Vercel. Namun fitur Admin CMS saat ini
masih prototype berbasis browser:

- Konten disimpan di `localStorage` browser yang digunakan untuk mengedit. Perubahan tidak
  otomatis tersinkron ke browser pengunjung atau perangkat lain.
- Login demo masih tertanam di file HTML (`admin / sukasari123`), bukan autentikasi server.
- Upload poster promo disimpan di browser, bukan di penyimpanan cloud bersama.

Karena itu, **jangan gunakan login demo untuk melindungi data atau menganggap perubahan Admin
sudah tampil untuk seluruh pengunjung**. Sebelum mengoperasikan CMS secara publik, hubungkan
login ke Supabase Auth, konten ke Supabase Database, dan gambar ke Supabase Storage; aktifkan
Row Level Security (RLS) dengan policy yang sesuai. Hapus kredensial demo dari HTML setelah
backend admin siap.

## Edit konten untuk uji coba

Buka website lalu akses menu Admin CMS di bagian footer. Kredensial demo:
- Username: `admin`
- Password: `sukasari123`

Perubahan hanya tersimpan pada browser yang sedang digunakan.
