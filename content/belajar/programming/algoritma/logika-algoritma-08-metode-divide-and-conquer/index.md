---
title: "Logika dan Algoritma #08: Metode Divide and Conquer"
description: "Metode Divide and Conquer adalah pendekatan dalam pemecahan masalah yang membagi masalah menjadi bagian-bagian kecil, menyelesaikan masing-masing bagian, lalu menggabungkan hasilnya."
tags: ["belajar", "coding", "algoritma", "logika", "divide and conquer"]
series: ["Chapters Logika dan Algoritma"]
series_order: 8
date: 2026-04-18T05:02:50+07:00
draft: false
---

## Metode D And C

#### Divide

Memilah data nilai elemen–elemen dari rangkaian data menjadi dua bagian dan mengulangi pemilahan hingga satu elemen terdiri maksimal dua nilai (Sonita & Nurtaneo, 2015).

#### Conquer

Mengurutkan masing-masing data nilai elemen (Sonita & Nurtaneo, 2015).

#### Prinsip Dasar

- Membagi n input menjadi k subset input yang berbeda (1<k≤n).
- k subset input tersebut akan terdapat k subproblem.
- Setiap subproblem mempunyai solusi menjadi k subsolusi.
- Dari k subsolusi akan mendapatkan solusi yang optimal **Jika subproblem masih besar → D and C**

## Bentuk Umum Proses Metode D And C dpt dilihat sebagai berikut:

{{< mermaid >}}
flowchart TD
%% Node Puncak
Top["n input"]

    %% Level 1: Pembagian Input
    In1["n input I"]
    In2["n input II"]
    In3["n input III"]
    InK["n input K"]

    %% Level 2: Subproblem
    Prob1["Subproblem I"]
    Prob2["Subprob. II"]
    Prob3["Subprob. III"]
    ProbK["Subprob. K"]

    %% Level 3: Subsolusi
    Sol1["Subsolusi I"]
    Sol2["Subsolusi II"]
    Sol3["Subsolusi III"]
    SolK["Subsolusi K"]

    %% Node Bawah: Solusi Gabungan
    Final["Solusi Optimal"]

    %% --- Alur Panah ---

    %% Dari Top ke Input cabang
    Top --> In1
    Top --> In2
    Top --> In3
    Top --> InK

    %% Dari Input cabang ke Subproblem
    In1 --> Prob1
    In2 --> Prob2
    In3 --> Prob3
    InK --> ProbK

    %% Dari Subproblem ke Subsolusi
    Prob1 --> Sol1
    Prob2 --> Sol2
    Prob3 --> Sol3
    ProbK --> SolK

    %% Dari Subsolusi digabung ke Solusi Optimal
    Sol1 --> Final
    Sol2 --> Final
    Sol3 --> Final
    SolK --> Final

{{< /mermaid >}}

- Metode D AND C
  Menggunakan teknik Rekursif yang membagi masalah menjadi dua atau lebih submasalah dengan ukuran yang sama. Masalah umum untuk teknik ini seperti pengurutan, perkalian.

- Metode D AND C:

1. Merge Sorting
2. Quick Sorting
3. Binary Search
4. Teknik D and C

## Merge Sort

- Menggabungkan dua array yang sudah terurut (Utami, 2017)
- Metode merge sort merupakan metode yang membutuhkan fungsi rekursif untuk penyelesaiannya.

#### Prinsip Kerja Merge Sort adalah :

- Kelompokkan deret bilangan kedalam 2 bagian, 4 bagian, 8 bagian, ......dst sampai tinggal sendiri
- Lakukan pengurutan sesuai dengan kelompok sebelumnya
- Lakukan pengurutan sejumlah pembagian

Contoh 1:

{{< mermaid >}}
flowchart TD
%% Level 1: Array Awal
L1["22 | 10 | 15 | 3 | 8 | 2"]

    %% Level 2: Pembagian Pertama
    L2_1["22 | 10 | 15"]
    L2_2["3 | 8 | 2"]

    %% Level 3: Pembagian Kedua
    L3_1["22 | 10"]
    L3_2["15"]
    L3_3["3 | 8"]
    L3_4["2"]

    %% Level 4: Pembagian Ketiga (Satuan)
    L4_1["22"]
    L4_2["10"]
    L4_3["3"]
    L4_4["8"]

    %% Level 5: Penggabungan (Merge) Pertama
    L5_1["10 | 22"]
    L5_2["15"]
    L5_3["3 | 8"]
    L5_4["2"]

    %% Level 6: Penggabungan Kedua
    L6_1["10 | 15 | 22"]
    L6_2["2 | 3 | 8"]

    %% Level 7: Hasil Akhir Terurut
    L7["2 | 3 | 8 | 10 | 15 | 22"]

    %% --- Alur Panah Divide (Memecah) ---
    L1 --> L2_1
    L1 --> L2_2

    L2_1 --> L3_1
    L2_1 --> L3_2

    L2_2 --> L3_3
    L2_2 --> L3_4

    L3_1 --> L4_1
    L3_1 --> L4_2

    L3_3 --> L4_3
    L3_3 --> L4_4

    %% --- Alur Panah Conquer (Menggabung) ---
    L4_1 --> L5_1
    L4_2 --> L5_1

    L3_2 --> L5_2

    L4_3 --> L5_3
    L4_4 --> L5_3

    L3_4 --> L5_4

    L5_1 --> L6_1
    L5_2 --> L6_1

    L5_3 --> L6_2
    L5_4 --> L6_2

    L6_1 --> L7
    L6_2 --> L7

{{< /mermaid >}}

Contoh 2:

<div style="display: flex; flex-direction: column; gap: 15px; font-family: sans-serif; font-size: 16px;">
  
  <div style="display: flex; align-items: center;">
    <div style="width: 85px;">Awal</div>
    <table style="border-collapse: collapse; text-align: center; margin: 0;">
      <tr>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">5</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">7</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">3</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">2</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">4</td>
      </tr>
    </table>
  </div>

  <div style="display: flex; align-items: center;">
    <div style="width: 85px;">Bagi 2</div>
    <table style="border-collapse: collapse; text-align: center; margin: 0;">
      <tr>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">5</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">7</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">3</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #00b050; color: #000;">2</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #00b050; color: #000;">4</td>
      </tr>
    </table>
  </div>

  <div style="display: flex; align-items: center;">
    <div style="width: 85px;">Bagi 4</div>
    <table style="border-collapse: collapse; text-align: center; margin: 0;">
      <tr>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">5</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">7</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #ffc000; color: #000;">3</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #00b050; color: #000;">2</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #92d050; color: #000;">4</td>
      </tr>
    </table>
  </div>

  <div style="display: flex; align-items: center;">
    <div style="width: 85px;">Bagi 8</div>
    <table style="border-collapse: collapse; text-align: center; margin: 0;">
      <tr>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">5</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #ff0000; color: #000;">7</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #ffc000; color: #000;">3</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #00b050; color: #000;">2</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #92d050; color: #000;">4</td>
      </tr>
    </table>
  </div>

  <div style="display: flex; align-items: center;">
    <div style="width: 85px;">Sorting 1</div>
    <table style="border-collapse: collapse; text-align: center; margin: 0;">
      <tr>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">5</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">7</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #ffc000; color: #000;">3</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #00b050; color: #000;">2</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #92d050; color: #000;">4</td>
      </tr>
    </table>
  </div>

  <div style="display: flex; align-items: center;">
    <div style="width: 85px;">Sorting 2</div>
    <table style="border-collapse: collapse; text-align: center; margin: 0;">
      <tr>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">3</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">5</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #323299; color: #000;">7</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #00b050; color: #000;">2</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #00b050; color: #000;">4</td>
      </tr>
    </table>
  </div>

  <div style="display: flex; align-items: center;">
    <div style="width: 85px;">Sorting 3</div>
    <table style="border-collapse: collapse; text-align: center; margin: 0;">
      <tr>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">2</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">3</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">4</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">5</td>
        <td style="border: 1px solid #000; width: 60px; padding: 5px 0; background-color: #fff; color: #000;">7</td>
      </tr>
    </table>
  </div>

</div>

```py
def mergeSort(X):
    print("Memecah array: ", X)

    if len(X) > 1:
        mid = len(X) // 2
        lefthalf = X[:mid]
        righthalf = X[mid:]

        # Rekursif untuk memecah array menjadi bagian terkecil
        mergeSort(lefthalf)
        mergeSort(righthalf)

        i = j = k = 0

        # Proses penggabungan (Merge) kembali secara terurut
        while i < len(lefthalf) and j < len(righthalf):
            if lefthalf[i] < righthalf[j]:
                X[k] = lefthalf[i]
                i = i + 1
            else:
                X[k] = righthalf[j]
                j = j + 1
            k = k + 1

        # Memasukkan sisa elemen dari lefthalf (jika ada)
        while i < len(lefthalf):
            X[k] = lefthalf[i]
            i = i + 1
            k = k + 1

        # Memasukkan sisa elemen dari righthalf (jika ada)
        while j < len(righthalf):
            X[k] = righthalf[j]
            j = j + 1
            k = k + 1

    print("Menggabungkan: ", X)

# --- Blok pemanggilan fungsi ---
X = [22, 10, 15, 3, 8, 2]
print("Array awal:", X)
print("-" * 30)

mergeSort(X)

print("-" * 30)
print("Hasil akhir:", X)
```

Hasil Program:

```
Array awal: [22, 10, 15, 3, 8, 2]
------------------------------
Memecah array:  [22, 10, 15, 3, 8, 2]
Memecah array:  [22, 10, 15]
Memecah array:  [22]
Menggabungkan:  [22]
Memecah array:  [10, 15]
Memecah array:  [10]
Menggabungkan:  [10]
Memecah array:  [15]
Menggabungkan:  [15]
Menggabungkan:  [10, 15]
Menggabungkan:  [10, 15, 22]
Memecah array:  [3, 8, 2]
Memecah array:  [3]
Menggabungkan:  [3]
Memecah array:  [8, 2]
Memecah array:  [8]
Menggabungkan:  [8]
Memecah array:  [2]
Menggabungkan:  [2]
Menggabungkan:  [2, 8]
Menggabungkan:  [2, 3, 8]
Menggabungkan:  [2, 3, 8, 10, 15, 22]
------------------------------
Hasil akhir: [2, 3, 8, 10, 15, 22]
```

## Quick Sorting

- Merupakan metode yang tercepat
- Quicksort diperkenalkan oleh C.A.R. Hoare. Quicksort partition exchange sort, karena konsepnya membuat bagian-bagian, dan sort dilakukan perbagian.
- Pada algoritma quick sort, pemilihan pivot merupaka hal yang menentukan apakah algoritma quicksort tersebut akan memberikan performa terbaik atau terburuk (Nugraheny, 2018).

Misal ada N elemen dalam keadaan urut turun, adalah mungkin untuk mengurutkan N elemen tersebut dengan N/2 kali, yakni pertama kali menukarkan elemen paling kiri dengan paling kanan, kemudian secara bertahap menuju ke elemen yang ada di tengah. Tetapi hal ini hanya bisa dilakukan jika tahu pasti bahwa urutannya adalah urut turun.

Secara garis besar metode ini dijelaskan sebagai berikut, Misal: akan mengurutkan vektor A yang mempunyai N elemen. Pilih sembarang dari vektor tsb, biasanya elemen pertama misalnya X. Kemudian semua elemen tersebut disusun dengan menempatkan X pada posisi J sedemikian rupa sehingga elemen ke 1 sampai ke j-1 mempunyai nilai lebih kecil dari X dan elemen ke J+1 sampai ke N mempunyai nilai lebih besar dari X.

Dengan demikian mempunyai dua buah subvektor, subvektor pertama nilai elemennya lebih kecil dari X, subvektor kedua nilai elemennya lebih besar dari X.

Pada langkah berikutnya, proses diatas diulang pada kedua subvektor, sehingga akan mempunyai empat subvektor. Proses diatas diulang pada setiap subvektor sehingga seluruh vektor semua elemennya menjadi terurutkan.

{{< mermaid >}}
flowchart TD
%% Level 1: Array Awal
L1["23 | 45 | 12 | 24 | 56 | 34 | 27 | 23 | 16"]

    %% Level 2: Pemecahan Pertama (Pivot 23)
    L2_1["12 | 23 | 16"]
    L2_2["23"]
    L2_3["45 | 24 | 56 | 34 | 27"]

    L1 -- "Subvektor Kiri" --> L2_1
    L1 --> L2_2
    L1 -- "Subvektor Kanan" --> L2_3

    %% Level 3
    L3_1["12"]
    L3_2["23 | 16"]
    L3_3["23"]
    L3_4["24 | 34 | 27"]
    L3_5["45"]
    L3_6["56"]

    L2_1 --> L3_1
    L2_1 --> L3_2
    L2_2 --> L3_3
    L2_3 --> L3_4
    L2_3 --> L3_5
    L2_3 --> L3_6

    %% Level 4
    L4_1["12"]
    L4_2["16"]
    L4_3["23"]
    L4_4["23"]
    L4_5["24"]
    L4_6["34 | 27"]
    L4_7["45"]
    L4_8["56"]

    L3_1 --> L4_1
    L3_2 --> L4_2
    L3_2 --> L4_3
    L3_3 --> L4_4
    L3_4 --> L4_5
    L3_4 --> L4_6
    L3_5 --> L4_7
    L3_6 --> L4_8

    %% Level 5: Hasil Akhir (Satuan Terurut)
    L5_1["12"]
    L5_2["16"]
    L5_3["23"]
    L5_4["23"]
    L5_5["24"]
    L5_6["27"]
    L5_7["34"]
    L5_8["45"]
    L5_9["56"]

    L4_1 --> L5_1
    L4_2 --> L5_2
    L4_3 --> L5_3
    L4_4 --> L5_4
    L4_5 --> L5_5
    L4_6 --> L5_6
    L4_6 --> L5_7
    L4_7 --> L5_8
    L4_8 --> L5_9

{{< /mermaid >}}

<div style="font-family: sans-serif; color: currentColor;">
  
  <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap;">
    <h2 style="text-decoration: underline; margin-bottom: 10px;">Contoh 2</h2>
    <div style="font-size: 1.2em;">Pilih vektor X &rarr; elemen pertama</div>
  </div>
  
  <h3 style="text-decoration: underline; margin-top: 0; margin-bottom: 30px;">Iterasi 1</h3>
  
  <table style="margin-left: 10%; font-size: 1.5em; font-weight: bold; text-align: center; border-collapse: separate; border-spacing: 35px 25px; border: none;">
    <tr>
      <td style="border: none;">22</td>
      <td style="border: none;">10</td>
      <td style="border: none;">15</td>
      <td style="border: none;">3</td>
      <td style="border: none;">8</td>
      <td style="border: none;">2</td>
    </tr>
    <tr>
      <td style="border: none;">22</td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
    </tr>
    <tr>
      <td style="border: none;">10</td>
      <td style="border: none;">15</td>
      <td style="border: none;">3</td>
      <td style="border: none;">8</td>
      <td style="border: none;">2</td>
      <td style="border: none;">22</td>
    </tr>
  </table>

</div>

<div style="font-family: sans-serif; color: currentColor;">

  <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; margin-top: 30px;">
    <h3 style="text-decoration: underline; margin-bottom: 10px;">Iterasi 2</h3>
    <div style="font-size: 1.2em;">Pilih lagi vektor X berikutnya</div>
  </div>
  
  <table style="margin-left: 10%; font-size: 1.5em; font-weight: bold; text-align: center; border-collapse: separate; border-spacing: 35px 25px; border: none;">
    <tr>
      <td style="border: none;">10</td>
      <td style="border: none;">15</td>
      <td style="border: none;">3</td>
      <td style="border: none;">8</td>
      <td style="border: none;">2</td>
      <td style="border: none; color: #cc0000;">22</td>
    </tr>
    <tr>
      <td style="border: none;">10</td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
    </tr>
    <tr>
      <td style="border: none;">3</td>
      <td style="border: none;">8</td>
      <td style="border: none;">2</td>
      <td style="border: none; color: #cc0000;">10</td>
      <td style="border: none;">15</td>
      <td style="border: none; color: #cc0000;">22</td>
    </tr>
  </table>

  <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; margin-top: 50px;">
    <h3 style="text-decoration: underline; margin-bottom: 10px;">Iterasi 3</h3>
    <div style="font-size: 1.2em;">Pilih lagi vektor X berikutnya</div>
  </div>
  
  <table style="margin-left: 10%; font-size: 1.5em; font-weight: bold; text-align: center; border-collapse: separate; border-spacing: 35px 25px; border: none;">
    <tr>
      <td style="border: none;">3</td>
      <td style="border: none;">8</td>
      <td style="border: none;">2</td>
      <td style="border: none; color: #cc0000;">10</td>
      <td style="border: none;">15</td>
      <td style="border: none; color: #cc0000;">22</td>
    </tr>
    <tr>
      <td style="border: none;">3</td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
      <td style="border: none;"></td>
    </tr>
    <tr>
      <td style="border: none;">2</td>
      <td style="border: none; color: #cc0000;">3</td>
      <td style="border: none;">8</td>
      <td style="border: none; color: #cc0000;">10</td>
      <td style="border: none;">15</td>
      <td style="border: none; color: #cc0000;">22</td>
    </tr>
  </table>

</div>

## Binary Search

**Binary Search (Untuk data yang sudah terurut)**
Digunakan mencari sebuah data pada himpunan data-data yang tersusun secara urut, yaitu data yang telah diurutkan dari besar ke kecil/sebaliknya. Proses dilaksanakan pertama kali pada bagian tengah dari elemen himpunan, jika data yang dicari ternyata < elemen bagian atasnya, maka pencarian dilakukan dari bagian tengah ke bawah

Algoritma **Binary Search**

1. Low = 1 , High = N
2. Ketika Low <= High Maka kerjakan langkah No .3, Jika tidak Maka kerjakan langkah No.7
3. Tentukan Nilai Tengah dengan rumus (Low + High) Div 2
4. Jika X < Nilai Tengah, Maka High = Mid –1, Ulangi langkah 1
5. Jika X > Nilai Tengah, Maka Low = Mid +1, Ulangi langkah 1
6. Jika X = Nilai Tengah, Maka Nilai Tengah = Nilai yang dicari
7. Jika X > High Maka Pencarian GAGAL

**Contoh:**

Data A = { 1, 3, 9, 11, 15, 22, 29, 31, 48 }
Dicari **3**

**Langkah Pencariannya:**

Langkah 1: Low = 1 dan High = 9<br>
Langkah 2: Low <= High (jika YA ke **L-3**, jika TDK ke **L-7**)<br>
Langkah 3: Mid = (1+9) div 2 = 5 yaitu **15**<br>
Langkah 4: 3 < 15, maka High = 5 – 1 = 4 yaitu **11**<br>
Langkah 1: Low = 1 dan High = 4<br>
Langkah 2: Low <= High<br>
Langkah 3: Mid = (1+4) div 2 = 2 yaitu **3**<br>
Langkah 4: 3 < 3, ke langkah 5<br>
Langkah 5: 3 > 3, ke langkah 6<br>
Langkah 6: 3 = 3 (Pencarian berhasil)<br>

#### Kodingan Program Binary Search

```py
def BinSearch(data, key):
    awal = 0
    akhir = len(data) - 1
    ketemu = False

    while (awal <= akhir) and not ketemu:
        tengah = (awal + akhir) // 2

        if key == data[tengah]:
            ketemu = True
            print('data', key, 'ditemukan diposisi', tengah + 1)
        elif key < data[tengah]:
            akhir = tengah - 1
        else:
            awal = tengah + 1

    if not ketemu:
        print('data tidak ditemukan')

# --- Data uji coba Anda ---
data = [1, 3, 9, 11, 15, 22, 29, 31, 48]
print("Array data:", data)
print("Mencari angka: 3")
print("-" * 30)

BinSearch(data, 3)
```

Hasil Program:

```
data 3 ditemukan diposisi 2
```

## Teknik D AND C

- Dengan Prinsip Dasar Metode Divide & Conquer akan dapat dipecahkan suatu permasalahan proses Searching elemen Max&Min dengan teknik D and C
- Menghasilkan solusi optimal menemukan nilai Maximum dan Minimum

- Contoh:

Tentukan elemen MaxMin suatu array A yang terdiri dari 9 bilangan :

<table style="border: none; font-size: 1.2em; width: 100%; max-width: 600px; text-align: left; font-family: sans-serif;">
  <tr>
    <td style="border: none; padding: 5px 15px;">A[1] = 22,</td>
    <td style="border: none; padding: 5px 15px;">A[4] = -8,</td>
    <td style="border: none; padding: 5px 15px;">A[7] = 17</td>
  </tr>
  <tr>
    <td style="border: none; padding: 5px 15px;">A[2] = 13,</td>
    <td style="border: none; padding: 5px 15px;">A[5] = 15,</td>
    <td style="border: none; padding: 5px 15px;">A[8] = 31</td>
  </tr>
  <tr>
    <td style="border: none; padding: 5px 15px;">A[3] = -5,</td>
    <td style="border: none; padding: 5px 15px;">A[6] = 60,</td>
    <td style="border: none; padding: 5px 15px;">A[9] = 47</td>
  </tr>
</table>

Penyelesaian **Teknik D and C**

A = {22,13, -5, -8, 15, 60, 17, 31, 47}

{{< mermaid >}}
flowchart TD
%% Level 1 (Root)
N1["1,9 | &nbsp;&nbsp;&nbsp;&nbsp;"]

    %% Level 2
    N2_1["1,5 | &nbsp;&nbsp;&nbsp;&nbsp;"]
    N2_2["6,9 | &nbsp;&nbsp;&nbsp;&nbsp;"]

    %% Level 3
    N3_1["1,3 | &nbsp;&nbsp;&nbsp;&nbsp;"]
    N3_2["4,5 | &nbsp;&nbsp;&nbsp;&nbsp;"]
    N3_3["6,7 | &nbsp;&nbsp;&nbsp;&nbsp;"]
    N3_4["8,9 | &nbsp;&nbsp;&nbsp;&nbsp;"]

    %% Level 4
    N4_1["1,2 | &nbsp;&nbsp;&nbsp;&nbsp;"]
    N4_2["3,3 | &nbsp;&nbsp;&nbsp;&nbsp;"]

    %% --- Alur Panah Pembagian ---
    N1 --> N2_1
    N1 --> N2_2

    N2_1 --> N3_1
    N2_1 --> N3_2

    N2_2 --> N3_3
    N2_2 --> N3_4

    N3_1 --> N4_1
    N3_1 --> N4_2

{{< /mermaid >}}

#### Penyelesaian Teknik D AND C

Lalu Proses tree call dr setiap elemen yang ditunjuk pada bagan tree tersebut diatas. Dengan cara, membalik terlebih dahulu posisi tree dari bawah ke atas. Lalu mengisinya dengan elemen-elemnnya sesuai dengan bagan tree.

Perhatikan bagan tree call ini :

A = { 22, 13, -5, -8, 15, 60, 17, 31, 47 }

<div style="display: flex; justify-content: flex-end; align-items: center; margin-bottom: -20px; font-family: sans-serif;">
  <span style="font-size: 1.2em; margin-right: 15px;">Posisi penggabungan &rarr;</span>
  <span style="background-color: #add8e6; padding: 5px 15px; border: 1px solid #000; color: #000; font-size: 1.2em;">Max, Min</span>
</div>

{{< mermaid >}}
flowchart TD
%% Level 1 (Daun/Posisi Awal di Atas)
N12["1,2 | 22,13"]
N33["3,3 | -5,-5"]
N45["4,5 | -8,15"]
N67["6,7 | 60,17"]
N89["8,9 | 31,47"]

    %% Level 2 (Penggabungan Tahap 1)
    N13["1,3 | 22,-5"]

    %% Level 3 (Penggabungan Tahap 2)
    N15["1,5 | 22,-8"]
    N69["6,9 | 60,17"]

    %% Level 4 (Akar/Hasil Akhir di Bawah)
    N19["1,9 | 60,-8"]

    %% --- Alur Garis (Menggunakan --- untuk garis lurus tanpa panah) ---
    N12 --- N13
    N33 --- N13

    N13 --- N15
    N45 --- N15

    N67 --- N69
    N89 --- N69

    N15 --- N19
    N69 --- N19

{{< /mermaid >}}
