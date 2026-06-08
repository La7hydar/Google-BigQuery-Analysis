# 🚀 Google Analytics E-Commerce Interactive Dashboard (Power BI)

Sebuah dashboard Power BI interaktif berpenampilan premium yang didesain menggunakan tema modern **Midnight Navy & Cyberpunk Neon**. Proyek ini menganalisis perilaku pengguna, kategori perangkat (*device*), dan distribusi geografis data e-commerce Google Analytics dalam batas waktu pengerjaan kilat selama **2 hari**.

---

## 📌 Ringkasan Proyek & Keunikan
Dashboard ini mengubah log data mentah Google Analytics menjadi wawasan bisnis yang interaktif. Untuk memaksimalkan estetika dan kenyamanan visual, dashboard ini menghindari template standar bawaan pabrik dan menerapkan trik desain khusus:
* **Custom Geometric Charts:** Grafik Donut 3 bagian unik yang memanfaatkan potongan *dummy* tersembunyi sebesar $1/4$ di pojok atas-kiri. Area kosong ini dimanfaatkan secara estetik untuk menaruh judul metrik dan menghemat ruang (*whitespace*).
* **True/False Gauge KPI:** Menggunakan Gauge Chart bawaan yang dikalibrasi ulang untuk menampilkan persentase murni pengguna Mobile (`isMobile`), disesuaikan dengan bahasa desain Google versi *dark-mode*.
* **Interaksi Super Responsif:** Sinkronisasi filter yang mendalam di semua grafik, kartu KPI, dan tombol navigasi halaman.

---

## 📅 Garis Waktu & Eksekusi Cepat (Selesai dalam 2 Hari)

Proyek ini direkayasa, dibersihkan, divalidasi, dan didesain dari nol hingga selesai hanya dalam waktu **48 jam**:
* **Hari 1 (Data Engineering):** Proses penarikan data (*ingestion*), pemahaman skema, penanganan nilai kosong (*missing values*), dan pembuatan rumus dasar DAX.
* **Hari 2 (UI/UX Design):** Penyusunan tata letak (*wireframing*), penyesuaian trik geometri visual, pewarnaan tema gelap, dan uji coba interaksi (*QA Testing*).

---

## 📥 1. Sumber Data (Sourcing)
Dataset yang digunakan berasal dari **Google Analytics Sample Dataset (BigQuery / Google Merchandise Store)**.
* **Tipe Data:** Data web analytics berbasis sesi (*session*) dan hit-level.
* **Dimensi Utama:** `deviceCategory`, `isMobile`, `country`, `date`.
* **Metrik Utama:** `visitNumber`, `visitId` (digunakan untuk menghitung total kunjungan unik).

---

## 🧹 2. Proses Pembersihan & Penyiapan Data (Cleaning & Prep)
Agar data siap pakai di dalam Power BI dalam waktu 2 hari, langkah-langkah *data engineering* berikut telah dilakukan:

### Transformasi Data
1.  **Format Tipe Data:** Mengubah teks boolean mentah menjadi flag sistem yang absolut (misalnya, mengubah format kolom `isMobile` menjadi format `TRUE/FALSE` murni).
2.  **Agregasi Data:** Memangkas data log aktivitas yang sangat besar untuk fokus pada metrik kunjungan utama (`visitNumber` dan `visitId`) demi mempercepat waktu *loading* grafik.
3.  **Optimasi Top 7:** Menerapkan logika filter tingkat visual pada dimensi negara (`country`) untuk menyajikan **Top 7 Countries by Visit**, sehingga tabel menjadi ringkas dan membuang ratusan baris data kecil yang kurang berdampak.

### Logika Rumus DAX Measures (Trik Canggih)
Agar visualisasi dapat menampilkan efek khusus, data mentah tidak langsung ditarik ke dalam grafik, melainkan diolah menggunakan rumus DAX:
* **Trik Donut Transparan 3 Bagian:** Menghitung potongan *dummy* sebesar $25\%$ yang proporsional terhadap total data untuk memicu efek donat terpotong huruf C (`Donut_Sapi_Transparan = [Total_Semua_Device] * (1/3)`).
* **Persentase Aman:** Menggunakan fungsi `DIVIDE()` pada Gauge Chart untuk mencegah terjadinya error pembagian dengan angka nol (*zero-division bug*).

---

## 🌟 3. Kelebihan & "Superpower" Dashboard Ini
Mengapa dashboard ini jauh lebih unggul dibandingkan laporan standar biasa?

1.  **Palet Midnight Navy Premium (Bukan Hitam Pekat):** Menggunakan warna dasar samudra gelap `#0B0E14` dan panel kotak `#161B26` yang dipadukan dengan neon ungu `#A370F7` dan biru elektrik `#4D7CFF`. Menghindari mata lelah akibat kontras hitam-putih yang terlalu tajam.
2.  **Layout Presisi Tanpa Magnet:** Mematikan fitur `Snap to Grid` bawaan Power BI agar penempatan objek visual bisa digeser pixel-demi-pixel secara super presisi demi estetika dashboard yang seimbang.
3.  **Navigasi Halaman Instan:** Pindah halaman mulus menggunakan aset gambar yang diberi perintah *Action Page Navigation*, menghilangkan tab menu bawaan yang kaku.
4.  **Sinkronisasi Filter Anti-Gagal:** Pembuatan rumus DAX murni memastikan bahwa ketika pengguna mengklik potongan grafik *Desktop* atau *Mobile*, angka di Card KPI besar otomatis ikut berubah memfilter data secara instan.

---

## 🛠️ Cara Menjalankan Proyek Ini
1. Clone repository ini atau unduh file `.pbix` yang tersedia.
2. Buka file tersebut menggunakan aplikasi **Power BI Desktop**.
3. *Tips saat mengedit:* Untuk menguji tombol navigasi halaman di dalam Power BI Desktop, tahan tombol **`Ctrl` pada keyboard lalu klik** gambar navigasi tersebut!

---
*Dikembangkan dengan 💡 dan 🚀 hanya dalam waktu 2 Hari.*
