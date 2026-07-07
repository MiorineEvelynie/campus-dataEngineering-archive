# End-to-End Data Engineering Pipeline: Online Retail Analytics

## Project Overview
Proyek ini bertujuan untuk membangun *end-to-end data engineering pipeline* untuk mengubah *raw data* ritel menjadi *insight* analitis menggunakan Power BI. Data sumber yang digunakan adalah dataset CSV *Online Retail Transaction* asli berbasis di Inggris yang terdiri dari 541.910 baris. Data mentah ini memiliki beberapa masalah seperti *duplicate records*, *missing values*, dan *inconsistent transactions* yang perlu diatasi sebelum dapat digunakan secara langsung untuk *sales & customer behaviour analysis* serta *product performance monitoring*.

## Tech Stack & Architecture
Proyek ini mengimplementasikan pendekatan ETL (Extract, Transform, Load) karena transformasi data dilakukan sebelum dimuat ke MySQL, yang dinilai lebih cocok untuk analisis ritel guna memastikan data lebih *reliable*, mudah divalidasi, dan terstruktur lebih bersih.
*   **Data Source:** File CSV (*raw data source*).
*   **Preprocessing:** Python digunakan untuk *initial preprocessing*.
*   **ETL Orchestration:** Pentaho Data Integration digunakan untuk mengatur eksekusi *pipeline* ETL secara berurutan, mulai dari *data ingestion*, pembuatan *dimension table*, hingga *fact table*.
*   **Data Storage:** MySQL digunakan sebagai *database* relasional yang terstruktur untuk menyimpan hasil proses ETL.
*   **Data Visualization:** Power BI digunakan untuk membangun *dashboard* interaktif.

## Data Modeling
Data dimodelkan menggunakan pendekatan **Star Schema**. Skema ini dipilih karena sangat optimal untuk kebutuhan analitik, memudahkan integrasi dengan Power BI, dan mempercepat proses *reporting queries*.
*   **Fact Table:** `fact_sales` (memuat metrik dan kalkulasi utama seperti *Quantity*, *UnitPrice*, dan *TotalSales*).
*   **Dimension Tables:** `dim_customer`, `dim_product`, dan `dim_time`.

## Data Quality & Reliability Assurance
Untuk memastikan kualitas dan keandalan data (*trustworthy data*), proyek ini menerapkan strategi berikut:
*   Membersihkan data dengan menghapus baris duplikat, menangani *null value*, dan memvalidasi tipe data.
*   Menerapkan aturan validasi (*validation rules*) yang ketat: `quantity > 0` dan `unit_price > 0`.
*   Menjaga reliabilitas dengan *workflow* ETL yang terstruktur, transformasi data yang terkontrol, pengecekan konsistensi, serta deteksi transaksi yang tidak valid.

## Analytical Insights
Berdasarkan *dashboard* Power BI yang dihasilkan, terdapat beberapa temuan bisnis utama:
*   Perusahaan memiliki 4.338 pelanggan yang loyal, dengan dominasi transaksi dari pelanggan lama.
*   Mayoritas pelanggan sering melakukan *check out* transaksi pada jam makan siang (pukul 12.00 - 13.00).
*   Terdapat tren lonjakan transaksi pada bulan Oktober - November, yang mengindikasikan pelanggan melakukan *restock* barang menjelang libur akhir tahun (Natal dan Tahun Baru).
*   Perusahaan memiliki arus pendapatan (*revenue*) yang sehat, mencapai sekitar £400K - £500K per bulan.
*   Penjualan terbesar berasal dari basis pelanggan di United Kingdom, dengan produk yang paling sering dibeli adalah *Paper Craft, Little Birdie*.

## Team (Kelompok 11)
Proyek Data Engineering (2026) ini dikerjakan oleh:
*   Keisa Putri Alisa (2802456662) - Preprocessing Data, Pipeline ETL & Database, Documentation
*   Raymond Widjaja (2802474406) - Preprocessing Data, Pipeline ETL & Database, Documentation
*   R. Divika Rathi (2802535963) - Power BI Dashboard & Documentation
