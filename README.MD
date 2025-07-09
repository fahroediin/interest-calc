
# Kalkulator Simulasi Pinjaman

Sebuah kalkulator pinjaman berbasis web yang dibuat dengan HTML, CSS, dan JavaScript murni (native) untuk mensimulasikan berbagai jenis skema bunga pinjaman.


## Fitur Utama

-   **Perhitungan Akurat**: Menggunakan rumus anuitas standar (setara dengan fungsi `PMT` di Microsoft Excel) untuk jenis bunga Fixed, Floating, Capped, dan Hybrid.
-   **Beragam Jenis Bunga**: Mendukung 6 jenis skema perhitungan yang umum:
    1.  **Fixed (Anuitas)**
    2.  **Floating (Anuitas)**
    3.  **Capped (Anuitas)**
    4.  **Flat**
    5.  **Effective Rate (EAR)**
    6.  **Hybrid (Anuitas)**
-   **Antarmuka Dinamis**: Form input akan secara otomatis menyesuaikan diri berdasarkan jenis bunga yang dipilih, menampilkan atau menyembunyikan field yang relevan.
-   **Tanpa Dependensi**: Dibuat sepenuhnya dengan HTML, CSS, dan JavaScript murni, tanpa memerlukan *framework* atau *library* eksternal.
-   **Desain Responsif**: Tampilan yang bersih dan mudah digunakan di berbagai ukuran layar, dari desktop hingga mobile.
-   **Format Rupiah**: Hasil perhitungan angsuran ditampilkan dalam format mata uang Rupiah (IDR) yang jelas, lengkap dengan dua angka desimal.

## Cara Menggunakan

1.  Salin seluruh kode dari file `.html` yang disediakan.
2.  Simpan kode tersebut ke dalam sebuah file dengan ekstensi `.html` (misalnya, `kalkulator.html`).
3.  Buka file tersebut menggunakan browser web modern apa pun (seperti Google Chrome, Firefox, atau Edge).
4.  Isi data pinjaman pada form yang tersedia:
    -   **Principal (Pokok Pinjaman)**
    -   **Interest Rate (% per Tahun)**
    -   **Tenor (Bulan)**
5.  Pilih **Interest Type** yang ingin Anda simulasikan dari menu dropdown.
6.  Jika diperlukan (untuk tipe Capped atau Hybrid), isi field tambahan yang muncul.
7.  Klik tombol **"Calculate"**.
8.  Hasil perhitungan akan ditampilkan di bawah form.

## Penjelasan Metode Perhitungan

Berikut adalah logika yang digunakan untuk setiap jenis bunga:

-   **Fixed (Anuitas)**
    Menghitung angsuran bulanan yang tetap selama masa pinjaman menggunakan rumus anuitas standar. Hasilnya akan sama dengan fungsi `=PMT()` di Excel.

-   **Floating (Anuitas)**
    Menggunakan rumus anuitas yang sama dengan Fixed Rate. Perbedaannya adalah hasil perhitungan ini merupakan estimasi angsuran saat ini. Angsuran di masa depan dapat berubah mengikuti fluktuasi suku bunga acuan.

-   **Capped (Anuitas)**
    Mirip dengan Floating, namun dengan batas atas (cap). Kalkulator akan membandingkan suku bunga yang dimasukkan dengan *Cap Rate*. Jika suku bunga input lebih tinggi, perhitungan akan otomatis menggunakan *Cap Rate*.

-   **Flat**
    Menggunakan metode perhitungan bunga flat, di mana bunga dihitung dari total pokok pinjaman awal dan tidak berubah sepanjang tenor. Angsuran dihitung dengan rumus:
    `(Pokok Pinjaman / Tenor) + ((Pokok Pinjaman * Suku Bunga Tahunan) / 12)`

-   **Effective Rate (EAR)**
    Kalkulator ini tidak menghitung angsuran, melainkan **Suku Bunga Efektif Tahunan**. Ini menunjukkan biaya bunga riil per tahun setelah memperhitungkan efek bunga majemuk (compounding) bulanan.

-   **Hybrid (Anuitas)**
    Mensimulasikan pinjaman dengan dua periode bunga:
    1.  **Periode Fixed:** Menghitung angsuran awal menggunakan suku bunga tetap.
    2.  **Periode Floating:** Menghitung ulang angsuran berdasarkan sisa pokok pinjaman setelah periode fixed berakhir dan menggunakan suku bunga floating yang baru.

## Teknologi yang Digunakan

-   **HTML5**: Untuk struktur dan konten halaman.
-   **CSS3**: Untuk styling, layouting (Flexbox), dan desain responsif.
-   **JavaScript (ES6+)**: Untuk semua logika kalkulasi, manipulasi DOM, dan interaktivitas form.

---

### Disclaimer

Kalkulator ini dibuat untuk tujuan simulasi dan edukasi. Hasil perhitungan merupakan **estimasi** dan mungkin berbeda dengan perhitungan akhir dari lembaga keuangan yang dapat mencakup biaya tambahan seperti administrasi, provisi, atau asuransi. Selalu konfirmasikan dengan pihak bank atau lembaga keuangan Anda untuk mendapatkan rincian resmi.
