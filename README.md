# Superstore Data Analysis & Profitability Optimization Project 📊🚀

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Data Tool](https://img.shields.io/badge/Tools-Python%20%7C%20Tableau%20%7C%20Power%20BI-blue)
![Domain](https://img.shields.io/badge/Domain-Retail%20%26%20E--Commerce-orange)

## 📌 Business Overview & Problem Statement
Dalam bisnis retail skala besar, pertumbuhan pendapatan (*sales*) yang tinggi tidak selalu mencerminkan kesehatan finansial perusahaan jika tidak diimbangi dengan profitabilitas yang sehat. 

Pada dataset **Superstore**, tercatat total penjualan sebesar **$2,3 Juta** dengan laba bersih **$286 Ribu** (Profit Margin: **12,47%**). Meskipun secara makro perusahaan terlihat menghasilkan untung, analisis mendalam menunjukkan adanya kebocoran profit yang masif: **26,08% dari total transaksi (1.318 order) justru mengalami kerugian**.

Proyek ini bertujuan untuk menjawab pertanyaan bisnis krusial:
> **"Faktor apa yang paling berkontribusi terhadap terjadinya kerugian finansial di Superstore, dan bagaimana cara mengoptimalkan strategi pricing serta promosi tanpa mengorbankan volume penjualan?"**

---

## 🛠️ Repository Structure
```text
data-analyst-portfolio-project
│
├── README.md                    # Dokumentasi utama proyek
├── data/
│   └── sales_data.csv           # Dataset mentah / hasil pembersihan data
├── notebook/
│   └── analysis.ipynb           # Jupyter Notebook untuk Data Cleaning & EDA
├── dashboard/
│   └── superstore_dashboard.twbx # File Dasbor Interaktif (Tableau/Power BI)
├── output/
│   └── dashboard_preview.png    # Screenshot visualisasi dasbor untuk dokumentasi
└── report/
    └── executive_summary.pdf    # Laporan analisis berkas PDF formal
```
💻 Tech Stack & Data Pipelines
1. Data Cleaning & Preprocessing (Python)
Missing Value & Duplicate Check: Memastikan integritas data dengan validasi completeness mencapai 100% (9.994 baris data aman dari nilai kosong atau duplikat).

Data Type Standardization: Mengonversi objek teks Order Date dan Ship Date menjadi tipe data datetime64.

Text Cleaning: Melakukan stripping spasi berlebih dan standardisasi Title Case pada fitur kategori teks seperti Ship Mode, Segment, City, State, dan Category.

Outlier Analysis: Menggunakan metode IQR (Interquartile Range) untuk mengidentifikasi anomali data numerik (Sales, Quantity, Discount, Profit). Outlier dipertahankan karena bersifat organik dan merepresentasikan transaksi retail riil.

2. Feature Engineering
Menambahkan kolom kalkulasi bisnis baru untuk memperdalam analisis:

Shipping Days: Mengukur durasi pengiriman barang (Ship Date - Order Date).

Profit Margin: Mengukur efisiensi laba bersih terhadap nilai penjualan bersih dalam persentase.

Unit Price: Menghitung harga satuan produk sebelum dikenakan potongan diskon.

🔍 Key Insights & Data Exploration
1. Paradox Diskon vs Profitabilitas
Ditemukan korelasi negatif yang kuat antara besaran diskon dan profitabilitas: transaksi tanpa diskon hampir seluruhnya menghasilkan profit, sementara pemberian diskon tinggi secara agresif berpotensi besar memicu kerugian finansial.

Temuan Utama: Kerugian tidak semata-mata disebabkan oleh angka diskon yang besar, melainkan kebijakan diskon yang melebihi kapasitas produk untuk menyerap diskon (Base Margin).

2. Analisis Lini Produk: Margin Awal vs Diskon
Sub-Kategori Binders (Office Supplies): Memiliki Base Margin awal yang sangat tebal yaitu 48,04%. Meskipun diberikan rata-rata diskon tinggi sebesar 37,23%, Binders tetap menghasilkan keuntungan bersih yang aman (menyisakan margin positif +10,82%).

Sub-Kategori Tables (Furniture): Memiliki Base Margin dasar yang tipis sebesar 18,55%. Ketika perusahaan menerapkan rata-rata diskon sebesar 26,13%, margin terkikis habis hingga berujung pada kerugian total sebesar -$17.725 (selisih margin minus -7,58%).

Produk Penahan Kerugian Terbesar: Sub-kategori Tables (-$17,7K) dan Bookcases (-$3,4K) menjadi beban profit terbesar akibat promo diskon yang tidak terkendali.

💡 Strategic Recommendations
Berdasarkan hasil analisis visual data, berikut adalah rekomendasi strategis untuk manajemen Superstore demi mengoptimalkan profit:

Restrukturisasi Batas Maksimum Diskon (Dynamic Discount Ceiling):
Kebijakan diskon tidak boleh disamaratakan (one-size-fits-all). Batasi diskon secara ketat berdasarkan kategori produk. Untuk sub-kategori bermargin tipis seperti Furniture, batas diskon aman wajib berada di bawah 18%.

Evaluasi Struktur Harga Dasar (Pricing Review):
Lakukan peninjauan kembali pada harga dasar Tables dan Bookcases. Tingkatkan efisiensi biaya logistik atau naikkan harga satuan dasar agar memiliki Base Margin yang lebih tebal sebelum dipasarkan dengan skema promo.

Fokus Promosi pada Produk High-Margin:
Alihkan anggaran kampanye pemasaran atau promo diskon besar ke segmen Technology (seperti Copiers dan Phones). Segmen ini memiliki struktur margin dasar yang sangat kuat sehingga tetap profitable meskipun diberikan diskon hingga 30%.

🖥️ Interactive Dashboard Preview
Berikut adalah gambaran dasbor interaktif Executive Profitability Overview yang dibangun untuk membantu jajaran manajemen mengambil keputusan berbasis data secara real-time:

Proyek ini diselesaikan sebagai bagian dari portofolio profesional Data Analytics (2026).


👤 Author

Benedictus Irvanda Nugroho

Data Analytics Portfolio Project (2026)

Focused on transforming business data into actionable insights through data cleaning, exploratory data analysis, visualization, and business intelligence reporting.
