# UTS Graf Sains Data - Sistem Rekomendasi Berbasis Graf dan KNN

Repositori ini berisi implementasi dan laporan lengkap Ujian Tengah Semester (UTS) mata kuliah Graf Sains Data. Proyek ini mengimplementasikan Sistem Rekomendasi E-Commerce berbasis jaringan/graf menggunakan Neo4j, Vector Space Model (VSM), dan Item-based KNN (Cosine Similarity) pada Retail Rocket Dataset.

---

## Deskripsi Proyek
Proyek ini bertujuan untuk membangun dan mengevaluasi model rekomendasi produk dengan mengorelasikan interaksi Visitor dan Item pada data e-commerce. Model memanfaatkan kueri Cypher Neo4j untuk menghitung kemiripan item berdasarkan Cosine Similarity vektor interaksi pengguna.

---

## Struktur Repositori
* uts_bilqis_216.ipynb : Notebook Jupyter utama berisi kueri Cypher, pemrosesan VSM, visualisasi graf NetworkX, dan metrik evaluasi.
* events_p1_train.csv : Dataset Training periode P1 (1-30 Juni 2015).
* events_p2_test.csv : Dataset Testing periode P2 (1-15 Juli 2015).

---

## Visualisasi Subgraph Interaksi Graf (NetworkX)

Berikut adalah sampel struktur graf interaksi Bipartite (Item vs User) yang diekstrak dari dataset periode P1:

<img width="990" height="590" alt="image" src="https://github.com/user-attachments/assets/5a2376d4-515e-4390-8578-cf637f10e388" />

### Penjelasan Visualisasi:
1. Node Oranye (Item_...): Mewakili entitas Item (produk) sebagai objek pusat analisis.
2. Node Biru (User_...): Mewakili entitas Visitor (pengguna) yang berinteraksi dengan item.
3. Pola Co-Occurrence: Item yang sering dikunjungi oleh kelompok pengguna yang sama (seperti Item_367447 dan Item_253185) memiliki nilai Cosine Similarity yang tinggi, yang menjadi dasar algoritma Item-based KNN.

---

## Hasil Evaluasi Rekomendasi (Soal 2.2)

Evaluasi dilakukan pada visitor target untuk menguji performa rekomendasi top-k (k=5):

| Parameter / Metrik | Hasil Evaluasi |
| :--- | :--- |
| Target Visitor ID | 917504 |
| Top-5 Item Rekomendasi | [257655, 46109, 3342, 391629, 409492] |
| Top-3 Advertised Items | [257655, 46109, 3342] |
| Hit@5 | 0 |
| NDCG@5 | 0.0000 |

Catatan Analisis: Nilai metrik evaluasi 0 wajar terjadi pada pengujian sampel individu akibat tingginya tingkat sparsity data pada e-commerce implicit feedback. Namun, pipeline ekstraksi kueri Cypher KNN berbasis Cosine Similarity di Neo4j telah terbukti berjalan dengan sukses.

---
Disusun oleh Bilqis Fadiyah Nisrina (24031554216) - UTS Graf Sains Data
