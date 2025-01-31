# Deteksi Plat Nomor Menggunakan Python

Program ini dirancang untuk mendeteksi dan mengenali plat nomor kendaraan dari sebuah video. Proses deteksi dilakukan dengan menggunakan teknik pengolahan citra seperti konversi ke grayscale, peningkatan kontras, deteksi tepi (Canny Edge Detection), dan pencarian kontur. Setelah area plat nomor terdeteksi, teks pada plat nomor dibaca menggunakan EasyOCR, sebuah library Optical Character Recognition (OCR) yang mendukung berbagai bahasa, termasuk bahasa Inggris ('en').

---

## Fitur
- Deteksi plat nomor kendaraan dari video.
- Penggunaan Canny Edge Detection untuk mendeteksi tepi plat nomor.
- Pembacaan teks plat nomor menggunakan EasyOCR.
- Penyimpanan frame yang telah diproses ke dalam direktori output.
- Visualisasi hasil deteksi dengan kotak hijau dan teks plat nomor.

---

## Persyaratan
Berikut adalah daftar pustaka yang diperlukan untuk menjalankan proyek ini:
- Python 3.x
- OpenCV (`opencv-python`)
- NumPy (`numpy`)
- EasyOCR (`easyocr`)

Anda dapat menginstal pustaka yang diperlukan dengan perintah berikut:
```bash
pip install opencv-python numpy easyocr
```

---

## Cara Menjalankan Program
1. Clone repositori ini atau unduh file script Python.
2. Siapkan file video yang akan diproses dan simpan di direktori `assets` dengan nama `video.mp4`.
3. Jalankan script Python dengan perintah berikut:
   ```bash
   deteksiplat.py
   ```
4. Hasil deteksi akan disimpan di direktori `assets/processed_frames`.

---

## Struktur Direktori
```
/proyek-deteksi-plat-nomor
│
├── assets/
│   ├── video2.mp4                  # File video input
│   └── processed_frames/           # Direktori untuk menyimpan frame yang diproses
│
└── deteksiplat.py                  # Script utama untuk deteksi plat nomor
```

---

## Penjelasan Kode
### 1. Inisialisasi
- Program memuat video dari path yang ditentukan (`video_path`).
- Membuat direktori output (`output_dir`) untuk menyimpan frame yang telah diproses.
- Menginisialisasi EasyOCR Reader untuk membaca teks pada plat nomor.

### 2. Pengolahan Frame
- Setiap frame diubah ke grayscale dan ditingkatkan kontrasnya.
- Deteksi tepi dilakukan menggunakan Canny Edge Detection.
- Kontur dicari untuk mengidentifikasi area yang kemungkinan besar adalah plat nomor.

### 3. Deteksi Plat Nomor
- Area yang memenuhi kriteria rasio aspek (2 < aspect_ratio < 5) dipotong dan dikirim ke EasyOCR untuk membaca teks.
- Hasil pembacaan teks ditampilkan di atas kotak hijau yang mengelilingi plat nomor.

### 4. Penyimpanan Frame
- Frame yang telah diproses disimpan ke direktori output dengan nama file yang mencerminkan waktu (dalam detik) saat frame tersebut diambil.

---

## Contoh Output
- Frame yang telah diproses disimpan dalam direktori `assets/processed_frames` dengan nama file seperti `frame_0.png`, `frame_1.png`, dst.
- Pada setiap frame yang berhasil mendeteksi plat nomor, akan ditampilkan:
  - Kotak hijau di sekitar plat nomor.
  - Teks plat nomor yang berhasil dibaca.

---

## Catatan
- Program ini bekerja dengan asumsi bahwa plat nomor memiliki rasio aspek antara 2 dan 5.
- Akurasi deteksi dan pembacaan teks sangat bergantung pada kualitas video dan kondisi pencahayaan.
- Untuk meningkatkan akurasi, dapat dilakukan tuning pada parameter deteksi tepi dan kontur, serta menggunakan model OCR yang lebih baik.

---

## Kontribusi
Jika Anda ingin berkontribusi pada proyek ini, silakan buka _issue_ atau _pull request_. Semua kontribusi sangat diterima!

---

## Lisensi
Proyek ini dilisensikan di bawah [MIT License](LICENSE).

---

Dibuat dengan ❤️ oleh [Hardianto].
