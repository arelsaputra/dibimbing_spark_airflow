# Batch Processing dengan PySpark dan Apache Airflow

## Ikhtisar
Proyek ini mengimplementasikan batch processing menggunakan PySpark dan Apache Airflow. Tujuan tugas ini adalah untuk mengotomatisasi proses ETL (Extract, Transform, Load) dengan menggunakan DAG (Directed Acyclic Graph) dari Airflow. Data yang telah dibersihkan akan dibaca, diproses, dianalisis, dan hasilnya disimpan ke dalam PostgreSQL atau file CSV.

## Komponen Proyek
1. **Apache Airflow**: Digunakan untuk mengotomatisasi dan menjadwalkan tugas batch processing.
2. **PySpark**: Digunakan untuk membaca dan memproses dataset besar secara efisien.
3. **PostgreSQL**: Digunakan untuk menyimpan hasil data yang telah diproses.
4. **CSV**: Digunakan sebagai alternatif untuk menyimpan hasil jika PostgreSQL tidak digunakan.

## Langkah-langkah untuk Menyelesaikan Tugas

### 1. Menyiapkan Infrastruktur Batch Processing dengan Apache Airflow
- **Install Apache Airflow** dan konfigurasikan untuk menjadwalkan dan mengotomatisasi batch processing.
- Pastikan **PySpark** dapat berjalan dengan baik di lingkungan Airflow.

### 2. Membangun Airflow DAG untuk Batch Processing
- Buat **DAG** (Directed Acyclic Graph) di Apache Airflow untuk mengoordinasikan tugas-tugas.
- Tentukan urutan tugas yang harus dijalankan:
  - **Extract**: Membaca data yang telah dibersihkan (dari file CSV atau PostgreSQL).
  - **Transform**: Melakukan agregasi atau analisis data.
  - **Load**: Menyimpan data yang telah diproses ke PostgreSQL atau file CSV.

### 3. Melakukan ETL dengan PySpark
- **Extract**: Mengambil data yang telah dibersihkan dari sumber (CSV atau PostgreSQL).
- **Transform**: Menggunakan PySpark untuk transformasi data, seperti agregasi.
- **Load**: Menyimpan hasil analisis ke PostgreSQL atau file CSV.

### 4. Membaca Data dari PostgreSQL dengan PySpark
- Gunakan PySpark untuk membaca data dari PostgreSQL jika digunakan untuk penyimpanan data.

### 5. Menyimpan Hasil
- Menampilkan hasil di konsol dan menyimpan hasil ke file CSV atau tabel PostgreSQL.

## File yang Harus Dikirimkan
- **Airflow DAGs**: Skrip Python yang mendefinisikan Airflow DAG untuk batch processing.
- **Skrip PySpark**: Skrip Python untuk melakukan tugas ETL menggunakan PySpark.
- **Query PostgreSQL**: Query yang digunakan dalam pipeline untuk ekstraksi atau manipulasi data.
- **Dokumentasi**: Deskripsi rinci mengenai alur kerja, DAG, proses ETL, dan analisis batch. (Lihat [documentation.txt](dags/documentation.txt)).

## Cara Menjalankan Proyek
1. Pastikan **Apache Airflow** sudah terinstal dan berjalan.
2. Pastikan **PySpark** sudah terkonfigurasi dengan benar di lingkungan Anda.
3. Siapkan **PostgreSQL** dan buat tabel yang diperlukan untuk penyimpanan data.
4. Jadwalkan dan jalankan DAG di Apache Airflow dengan perintah berikut:
   ```bash
   airflow dags trigger batch_processing_dag
