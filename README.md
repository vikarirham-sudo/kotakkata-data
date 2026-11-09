# Kotak Kata – data TTS Harian

Repo ini menyimpan teka-teki **TTS Harian** untuk aplikasi Kotak Kata.
Aplikasi mengambil `daily.json` dari GitHub Pages setiap kali dibuka,
jadi teka-teki baru bisa ditambah **tanpa update aplikasi**.

## Isi
| File | Fungsi |
|---|---|
| `daily.json` | Semua teka-teki harian, satu per tanggal |
| `english.json` | Semua level Tebak English (Beginner, Intermediate, Advanced) |
| `index.html` | Halaman cek: menampilkan versi dan sampai tanggal berapa stoknya |
| `alat/tambah_harian.py` | Alat untuk membuat teka-teki baru dari daftar kata |
| `alat/contoh_kata.txt` | Contoh format daftar kata |

## Cara menambah teka-teki
1. Salin `alat/contoh_kata.txt`, isi tanggal dan 12–16 kata + soal per tanggal.
2. Di Mac, buka Terminal di folder ini lalu jalankan:
   ```
   python3 alat/tambah_harian.py alat/kata_baru.txt
   ```
   Program menyusun papan, menampilkannya, dan memperbarui `daily.json`.
3. Di GitHub: **Add file → Upload files**, tarik `daily.json` yang baru, lalu **Commit changes**.
4. Tunggu 1–2 menit. Pemain mendapat teka-teki baru saat membuka aplikasi.

Cara lain: kirim daftar kata ke Claude, minta dibuatkan `daily.json` baru, lalu upload.

## Stok saat ini
129 teka-teki bertema, 9 November 2026 sampai 17 Maret 2027, termasuk edisi spesial
(Hari Pahlawan, Hari Guru, Hari Ibu, Natal, Tahun Baru, Isra Mikraj, Imlek, Ramadan, Nyepi, Idulfitri).

## Aturan penting
- Jangan ubah teka-teki untuk **hari ini atau hari yang sudah lewat**. Pemain yang sudah mulai tetap memakai versi lama, jadi hasil antarpemain bisa beda.
- Jaga stok minimal **30 hari ke depan**. Kalau stok habis, aplikasi otomatis memakai teka-teki cadangan bawaan.
- Judul spesial (baris `@`) muncul di kartu beranda, misalnya "Spesial: Hari Kemerdekaan".

## Tebak English (`english.json`)
- Setiap level: `tier` (beginner/intermediate/advanced), `title`, dan `words` berisi `w` (kata Inggris, huruf besar tanpa spasi), `m` (arti), `c` (jenis kata), `x` (contoh kalimat yang memuat kata itu).
- Tambahkan level baru **di akhir daftar**. Jangan ganti judul level lama, karena progres bintang pemain disimpan berdasarkan tingkat + judul.
- Setelah diunggah, pemain mendapat level baru saat membuka aplikasi.
