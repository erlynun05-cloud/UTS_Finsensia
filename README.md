# Sistem Informasi Analisis Data Transaksi Toko — Business Intelligence

Aplikasi Python dengan antarmuka web untuk EDA, preprocessing, Apriori, K-Means/RFM, dashboard BI, serta ekspor Excel/CSV/PDF.

## Penting: GitHub Pages tidak dapat menjalankan aplikasi ini langsung

Aplikasi ini membutuhkan **backend Python** untuk memproses Excel dan menyediakan endpoint `/api/result`, `/upload`, dan ekspor. GitHub Pages hanya menyajikan situs statis. Gunakan GitHub untuk menyimpan kode dan Render Free Web Service untuk menjalankan backend. Jika halaman GitHub Pages menampilkan teks README ini, itu berarti Pages sedang menampilkan dokumentasi statis—bukan menjalankan aplikasi Python. Buka aplikasi dari URL Render (`https://...onrender.com`) setelah layanan Render berstatus **Live**.

## Menjalankan secara lokal

1. Pasang Python 3.10 (disarankan Python 3.10.14).
2. Buka terminal pada folder proyek.
3. Jalankan:

   ```bash
   python -m venv .venv
   ```

   Windows:

   ```bash
   .venv\\Scripts\\activate
   ```

   macOS/Linux:

   ```bash
   source .venv/bin/activate
   ```

4. Pasang dependensi dan jalankan aplikasi:

   ```bash
   pip install -r requirements.txt
   python SISTEM_UTS_BI.py
   ```

5. Buka alamat lokal yang tercetak di terminal. Akun lokal bawaan: `finsensia` / `51230138`.
6. Unggah file Excel yang memiliki sheet `Data_Raw`, `Data_Produk`, dan `Data_Pelanggan`.

## Deploy gratis dengan GitHub + Render

1. Buat repository GitHub baru. Untuk tugas kuliah, repository **Private** lebih aman jika kode berisi identitas atau materi yang tidak ingin dipublikasikan.
2. Unggah file proyek: `SISTEM_UTS_BI.py`, `requirements.txt`, `Procfile`, `.python-version`, `render.yaml`, `.gitignore`, dan `README.md`. Jangan unggah `.venv`, file `.env`, atau data transaksi pribadi.
3. Masuk ke Render dan pilih **New + → Web Service**, lalu hubungkan repository GitHub tersebut.
4. Jika Render tidak mendeteksi `render.yaml`, isi pengaturan:
   - Runtime: Python 3.10 (sesuaikan `PYTHON_VERSION` menjadi `3.10.14`)
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `python SISTEM_UTS_BI.py --no-browser`
   - Plan: Free
5. Pada Environment Variables, atur:
   - `APP_USERNAME` = username pilihanmu
   - `APP_PASSWORD` = kata sandi pilihanmu
6. Deploy dan tunggu status **Live**. Buka URL `https://...onrender.com` yang diberikan Render.
7. Login lalu unggah Excel melalui menu Unggah Data. File yang diunggah diproses di memori; pada layanan gratis, jangan menganggap data/hasil akan tersimpan permanen setelah restart atau redeploy.

## Batasan dan keamanan

- Layanan gratis dapat tidur saat tidak aktif sehingga pembukaan pertama mungkin lambat.
- Unggahan dibatasi maksimal 25 MB.
- Login pada aplikasi asal menggunakan pemeriksaan hash di sisi browser, **bukan autentikasi server yang kuat**. Jangan gunakan kata sandi penting atau data sensitif. Untuk demo publik, anggap siapa pun yang memiliki URL berpotensi mengakses aplikasi.
- Data Excel tidak disertakan dalam repository. Unggah file Excel yang sesuai setelah aplikasi berjalan.
- Hasil analisis membutuhkan waktu dan memori; file sangat besar dapat melebihi batas layanan gratis.
