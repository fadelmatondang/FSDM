#FSDM
Paket Pemodelan Dinamika Sistem Fuzzy

Proyek ini adalah versi terbaru dari paket Fuzzy Systems Dynamics Modeling (FSDM). Ini mencakup antarmuka pengguna grafis (Laboratorium Logika) untuk membangun model FSDM, menentukan skenario, menjalankan model pada skenario, dan menampilkan hasil. Menggunakan GUI untuk membangun model dan skenario memastikan bahwa model dan file skenario diformat dengan benar. Ini juga menyederhanakan proses menjalankan model dan menganalisis hasilnya. Pengguna mahir juga dapat menjalankan skenario model secara terprogram; memuat model dengan fungsi createFuzzyModel, memuat skenario dengan fungsi createFuzzyScenario, dan menjalankan model dengan fungsi runFuzzyModel.

Menginstal Paket dan Dependensi
Paket Fuzzy Systems Dynamics Modeling adalah paket untuk lingkungan bahasa komputasi R. Penggabungan FSDM ke dalam paket R menyederhanakan penginstalan semua perangkat lunak yang diperlukan untuk menggunakannya. Paket ini dikembangkan menggunakan versi R terbaru pada saat itu (3.6.0) dan belum diuji dengan versi yang lebih lama. Bahasa R dapat diinstal dari www.r-project.org. Ini gratis dan open source. Setelah R diinstal, FSDM dengan memulai konsol R dan menyalin dan menempelkan baris kode berikut ke dalamnya:

```
#Set CRAN mirror untuk instal package dependencies.

if (is.null(getOption("repos")["CRAN"])) {
  options(repos = c(CRAN = "https://cran.rstudio.com/"))
}
#Install devtools package jika belum.

if (!library("devtools", logical.return = TRUE)) install.packages("devtools")
#Install FSDM package dari GitHub

devtools::install_github("gregorbj/FSDM")

```

** Catatan **: Paket XML adalah salah satu dependensi yang akan diinstal jika belum diinstal di sistem Anda. Penginstalan yang berhasil mengharuskan pustaka perangkat lunak * lib2xml-dev * diinstal pada sistem Anda agar paket XML dapat dikompilasi dari file sumber. Saya menyarankan sebelum Anda menjalankan * devtools: install_github ("gregorbj / FSDM") * Anda memeriksa apakah paket XML telah diinstal dan menginstalnya jika belum. Jika pustaka perangkat lunak * lib2xml-dev * tidak diinstal di komputer Anda dan Anda menjalankan Ubuntu dan Debian, Anda dapat menginstalnya dengan menjalankan * sudo apt-get install libxml2-dev * di program terminal Linux yang Anda gunakan.

## Running
Anda mungkin ingin memulai dengan membuat folder proyek terlebih dahulu dan kemudian menyalin model dan skenario demonstrasi dari paket yang diinstal ke folder proyek Anda. Setelah Anda membuat folder proyek Anda, Anda dapat menyalin model / skenario demonstrasi ke sana dengan memasukkan yang berikut ini di konsol R. Ganti * "PROJECT_FOLDER_PATH" * dalam kode dengan jalur lengkap ke folder proyek (mis. "C: / My_FSDM_Project").
```
copyDemoModels("PROJECT_FOLDER_PATH")
```

Antarmuka pengguna grafis Laboratorium Logika dapat dimulai dengan memasukkan yang berikut ini di konsol R:
```
FSDM::runLogicLab()
```

Memulai Laboratorium Logika dengan cara ini akan membuka aplikasi di jendela browser web menggunakan browser web default untuk komputer Anda. Perhatikan bahwa aplikasi tidak bekerja dengan benar di browser Microsoft Edge karena grafik yang menunjukkan hasil tidak akan ditampilkan. Aplikasi ini berfungsi di browser Chrome, Firefox, dan Brave. Ini mungkin berfungsi di browser lain juga tetapi belum diuji. Jika browser default Anda adalah Microsoft Edge, Anda perlu mengubahnya ke salah satu browser lainnya.

Perhatikan bahwa setelah Anda menutup jendela browser tempat Laboratorium Logika berjalan, saat Anda mengembalikan fokus ke jendela konsol R, Anda perlu menekan tombol escape pada keyboard Anda untuk kembali ke baris perintah konsol.

Panduan pengguna di folder * dokumentasi * dari paket yang diinstal memberikan informasi tentang cara menggunakan Laboratorium Logika. Ini sudah usang sehubungan dengan beberapa fitur dan tampilan beberapa layar, tetapi akan memberi Anda beberapa orientasi dasar. Ini akan diperbarui dalam beberapa minggu mendatang dan tersedia sebagai sketsa R standar yang akan mudah dipanggil dari konsol R.

**Catatan**: Laboratorium Logika saat ini hanya memungkinkan Anda mengerjakan satu model dalam satu sesi. Jika Anda ingin beralih dari bekerja pada satu model ke model lainnya, Anda harus keluar dari Laboratorium Logika dan memulai ulang. Perhatikan bahwa Anda dapat mengerjakan sejumlah skenario dalam satu sesi.

