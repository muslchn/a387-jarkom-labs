# A387 Jarkom Labs

Proyek ini adalah web server Node.js untuk submission kelas jaringan komputer Dicoding. Aplikasi berjalan di port `8000`, sedangkan reverse proxy NGINX atau Apache2 disiapkan untuk menerima request di port `3000` dan meneruskannya ke aplikasi Node.js.

## Fitur

- Web server Express dengan endpoint `GET /` yang mengembalikan `Hello world!`.
- Endpoint tambahan `GET /me` yang mengembalikan username Dicoding.
- Konfigurasi NGINX sebagai reverse proxy dari port `3000` ke `8000`.
- Konfigurasi rate limit NGINX sebesar `6 request per menit`.
- Konfigurasi Apache2 alternatif sebagai reverse proxy dari port `3000` ke `8000`.

## Menjalankan Aplikasi Node.js

Pastikan Node.js minimal versi `14.15.4` dan NPM sudah terpasang.

```bash
npm install
npm run start
```

Setelah aplikasi berjalan, endpoint Node.js dapat diuji langsung melalui:

```bash
curl http://localhost:8000/
curl http://localhost:8000/me
```

## Berkas Konfigurasi Submission

Gunakan berkas berikut sebagai isi konfigurasi yang diminta pada submission:

- `konfigurasiNGINX_Muslichin.txt` untuk `/etc/nginx/sites-available/default`.
- `konfigurasiApache2_Muslichin.txt` untuk `/etc/apache2/sites-available/000-default.conf`.
- `ports_Muslichin.txt` untuk `/etc/apache2/ports.conf`.
- `app.js` sebagai berkas aplikasi Node.js.

Catatan untuk reviewer: proyek ini menyertakan konfigurasi NGINX dan Apache2. Jalankan salah satu reverse proxy saja pada satu waktu karena keduanya menggunakan port `3000`.
