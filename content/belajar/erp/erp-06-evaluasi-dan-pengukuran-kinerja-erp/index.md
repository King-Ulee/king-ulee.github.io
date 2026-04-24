---
title: "Enterprise Resource Planning (ERP): Evaluasi Dan Pengukuran Kinerja ERP"
description: "Evaluasi dan pengukuran kinerja ERP adalah langkah penting untuk memastikan bahwa sistem ERP yang diimplementasikan memberikan manfaat yang diharapkan. Dalam bab ini, kita akan membahas berbagai metrik dan pendekatan untuk mengevaluasi kinerja ERP."
tags:
  [
    "ERP",
    "Enterprise Resource Planning",
    "Evaluasi ERP",
    "Pengukuran Kinerja ERP",
    "Metrik Evaluasi ERP",
  ]
series: ["Chapters on ERP"]
series_order: 6
date: 2026-04-26T02:30:30+07:00
draft: false
---

## Pendahuluan

Tidak semua proyek teknologi informasi diperusahaan berjalan mulus. Faktor kesiapan SDM dlm perusahaan dan kualitas konsultan sbg mitra kerja sama belum tentu menjamin keberhasilan implementasi proyek sistem informasi.

Merupakan suatu kenyataan bahwa belum tentu setiap sumber daya manusia baik dari pihak perusahaan maupun pihak konsultan memiliki semangat yang sama dalam mengerjakan suatu proyek Sistem Informasi.

Perlunya pertimbangan dalam melakukan pemilihan sumber daya manusia yang tepat dalam menangani sebuah proyek sistem informasi. Adalah tugas manajemen untuk melakukan penyeleksian terhadap staff atau karyawan sebagai project leader yang tepat untuk terlibat aktif dan menangani proyek sistem informasi,dimana orang yang benar benar memiliki bersemangat untuk mengikuti proyek sistem informasi secara tuntas.

Menurut Richardus Eko Indrajit, untuk dapat memperlihatkan hubungan antar manfaat (value) bagi SDM perusahaan dan konsultan terhadap potensi keberhasilan sebuah proyek Sistem Informasi dapat terlihat dalam matrik berikut :

## Hubungan manfaat Sumber Daya Manusia

{{< mermaid >}}
quadrantChart
x-axis "Value for IT Konsultants: LOW" --> "HIGH"
y-axis "Value for Corporate People: LOW" --> "HIGH"
quadrant-1 "1 Win-win Project"
quadrant-2 "2 Knowledge Transfer"
quadrant-3 "4 Just for Fun"
quadrant-4 "3 Free R&D"
{{< /mermaid >}}

#### Kuadran Satu

Memiliki sebuah lingkungan dimana SDM dari kedua pihak merasa mendapatkan manfaat dari proyek yang dikerjakan. Dalam keadaan ini, biasanya proyek akan berjalan cukup lancar, karena semua pihak saling bekerja sama dgn baik. Tidak ada perasaan curiga dan ingin mendapatkan suatu dari keberhasilan proyek TI. Dilihat dari sisi keuangan proyek, biasanya prinsip “ value for money” menjadi pertimbangan utama. Dengan demikian, akan tercipta suasana”win-win”, yang merupakan keadaan ideal sebuah proyek dimana hal ini yang akan memperkecil resiko terjadinya kegagalan implementasi proyek TI.

#### Kuadran Dua

Mewakili sebuah situasi dimana hanya pihak perusahaan (klien) saja yang merasa mendapatkan banyak manfaat dari keterlibatan SDM didalam menangani proyek TI. Sementara pihak konsultan merasa tidak memperoleh manfaat yang signifikan dengan keberadaan proyek TI tersebut, sehingga pihak konsultan cenderung tidak banyak terlibat secara intens dalam proyek TI. Fenomena ini kadang membuat pihak perusahaan menuntut hal-hal yang lebih daripada semestinya(over demanding). Walaupun pada mulanya resiko kegagalan proyek TI cukup kecil, namun suasana yang berlarut-larut(jika proyek TI berjangka relatif panjang), maka akan dapat meningkatkan resiko kegagalan proyek TI. Hal ini disebabkan, karena pihak konsultan akan melakukan pekerjaan lain diluar proyek tersebut, sehingga akan menurunkan kualitas pemberian jasa konsultan

#### Kuadran Tiga

Merupakan situasi yang terbalik dari kuadran dua, dimana pihak konsultan yg merasa mendapatkan manfaat dengan adanya proyek TI. Sementara bagi pihak perusahaan, SDM merasa cenderung menjadi beban, sehingga dari pihak perusahaan akan menyerahkan kepada pihak konsultan untuk mengerjakan proyek TI. Keadaan ini, akan membuat pihak SDM perusahaan akan memberikan berbagai kritik sebagai manifestasi ketidaksetujuan terhadap berbagai hasil kerja yang dilakukan pihak konsultan.Keadaan ini akan membuat resiko kegagalan proyek yang tinggi, terlepas dari berkualitas atau tidaknya output yang dihasilkan dari proyek TI tersebut. Dan tidak sedikit terjadi keadaan dimana pihak perusahaan menjadi acuh tak acuh terhadap hasil kerja yang dilakukan pihak konsultan.

Pada situasi ini, pihak konsultan akan diuntungkan karena disamping mendapatkan jasa konsultan, juga dapat dijadikan sarana pelatihan, penelitian dan pengembangan TI bagi pihak konsultan.

#### Kuadran Empat

Kedua belah pihak dengan berbagai alasan dan kondisi, tidak memperoleh manfaat apapun dari proyek TI tersebut, sehingga kedua belah pihak biasanya sama – sama menginginkan agar proyek diselesaikan dengan cepat dan dengan kualitas seadanya(minimum quality). Tidak jarang terjadi pelanggaran etika bisnis oleh salah satu maupun kedua belah pihak, yg tentunya dapat menimbulkan resiko dikemudian hari

## Evaluasi Sistem Baru

Tujuan dari aktivitas review evaluasi sistem baru adalah :

1. Menentukan apakah tujuan dan objectivitas sistem tercapai
2. Menentukan apakah prosedur operasional, aktivitas operasi dan kontrol sudah sempurna
3. Menentukan apakah keperluan pengguna telah dipenuhi
4. Menentukan apakah batasan sistem perlu diperhatikan

## Tahapan Evaluasi Sistem

{{< mermaid >}}
flowchart TD
N1["1. Identifikasi apa yang akan dievaluasi"]
N2["2. Tentukan Kriteria Evaluasi"]
N3["3. Organisir kegiatan evaluasi"]
N4["4. Pengumpulan data<br/>(termasuk pengukuran)"]
N5["5. Maintain record history"]
N6["6. Analisis data performance"]
N7["7. Susun rekomendasi"]
N8["8. Lakukan tindakan koreksi"]
N9["9. Proses evaluasi hasil"]

    %% Alur utama ke bawah
    N1 --> N2
    N2 --> N3
    N3 --> N4
    N4 --> N5
    N5 --> N6
    N6 --> N7
    N7 --> N8
    N8 --> N9

    %% Alur umpan balik (garis yang kembali ke atas)
    N8 --> N3
    N9 --> N1

{{< /mermaid >}}

## Pemeliharaan Sistem ERP

Aktivitas pemeliharaan meliputi aksi korektif terhadap permasalahan yang ditemui, adaptasi prosedur untuk fitur atau kebutuhan baru yang diperlukan. Aktivitas pemeliharaan sistem ERP perfektif sebagai tanggapan atas upgrade aplikasi program , dan aktivitas pemeliharaan preventif untuk kegiatan administrasi rutin.

Secara garis besar, klasifikasi aktivitas pemeliharaan sistem ERP dapat dilihat pada tabel berikut :

| Jenis        | Tugas                             | Keterangan                                            |
| :----------- | :-------------------------------- | :---------------------------------------------------- |
| **korektif** | aplikasi program tambahan         | ada tambahan aplikasi program dari vendor             |
|              | troubleshooting                   | menyelesaikan masalah berdasarkan laporan pengguna    |
| **adaptif**  | transfer                          | implementasi fitur baru                               |
|              | testing                           | pengujian setelah ada perubahan                       |
|              | modifikasi                        | kostumisasi internal                                  |
|              | penyesuaian antar muka(interface) | implementasi antar muka dengan program lain           |
|              | upgrade versi                     | penyesuaian, perencanaan dengan aplikasi              |
|              | Administrasi                      | monitor respone time, ukuran file, back up, error log |
|              | monitoring alur kerja             | menelusuri aliran aktivitas pemeliharaan              |

## Pengembangan Sistem ERP

Perkembangan pola bisnis dan kemajuan teknologi informasi dan komunikasi, dapat mempengaruhi pola implementasi sistem ERP dimasa mendatang, antara lain:

1. Penggunaan aplikasi berbasis web, khususnya untuk memudahkan koordinasi dengan mitra kerja pada supply chain
2. Meningkatkan sistem yang menggunakan inteligensia buatan(artificial intelligent) untuk mendukung proses perencanaan
3. Meningkatkan penggunaan sistem ERP pada perusahaan berskala menengah, dgn teknologi yangg lebih stabil dan waktu implementasi yang relatif cepat dan biaya instalasi yang lebih mudah
   4.Sistem cenderung bersifat fleksibel dan modular(mendukung pendekatan implementasi best of breed)
   5.Meningkatnya dukungan pihak ketiga(bolt ons) sebagai penyedia aplikasi yang diakses oleh sistem antara(middleware)
