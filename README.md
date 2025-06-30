# Telco Customer Churn
----

![Image](https://github.com/user-attachments/assets/d2858965-f44e-43cb-b5d2-4e308f1150b7)


## Sumber Data
Kumpulan data yang digunakan dalam proyek ini berasal dari dataset publik milik IBM dan tersedia untuk umum. Dataset ini banyak digunakan untuk tujuan pembelajaran dan edukasi dalam topik Customer Churn Prediction.
Nama Dataset: Telco Customer Churn
Sumber: [IBM Sample Data on Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn).

| **Kolom**                  | **Deskripsi**                                                                                                                                |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **customerID**             | ID unik untuk setiap pelanggan. Hanya sebagai identifikasi, tidak digunakan dalam analisis.                                                  |
| **gender**                 | Jenis kelamin pelanggan: `Male` atau `Female`.                                                                                               |
| **SeniorCitizen**          | Status apakah pelanggan adalah warga senior: `Yes` jika usia ≥ 65, `No` jika tidak.                                                          |
| **Partner**                | Apakah pelanggan memiliki pasangan: `Yes` atau `No`.                                                                                         |
| **Dependents**             | Apakah pelanggan memiliki tanggungan (anak/orang tua): `Yes` atau `No`.                                                                      |
| **tenure**                 | Lama pelanggan telah berlangganan (dalam bulan).                                                                                             |
| **PhoneService**           | Apakah pelanggan memiliki layanan telepon rumah: `Yes` atau `No`.                                                                            |
| **MultipleLines**          | Apakah pelanggan memiliki lebih dari satu saluran telepon: `Yes`, `No`, atau `No phone service`.                                             |
| **InternetService**        | Jenis layanan internet: `DSL`, `Fiber optic`, atau `No` jika tidak berlangganan.                                                             |
| **OnlineSecurity**         | Apakah pelanggan memiliki layanan keamanan online: `Yes`, `No`, atau `No internet service`.                                                  |
| **OnlineBackup**           | Apakah pelanggan menggunakan layanan cadangan online.                                                                                        |
| **DeviceProtection**       | Apakah pelanggan memiliki perlindungan perangkat.                                                                                            |
| **TechSupport**            | Apakah pelanggan memiliki dukungan teknis.                                                                                                   |
| **StreamingTV**            | Apakah pelanggan menggunakan layanan streaming TV.                                                                                           |
| **StreamingMovies**        | Apakah pelanggan menggunakan layanan streaming film.                                                                                         |
| **Contract**               | Jenis kontrak pelanggan: `Month-to-month`, `One year`, atau `Two year`.                                                                      |
| **PaperlessBilling**       | Apakah pelanggan menerima tagihan tanpa kertas (melalui email): `Yes` atau `No`.                                                             |
| **PaymentMethod**          | Metode pembayaran yang digunakan pelanggan, misalnya: `Electronic check`, `Mailed check`, `Credit card`, atau `Bank transfer`.               |
| **MonthlyCharges**         | Jumlah tagihan bulanan pelanggan.                                                       |
| **TotalCharges**           | Total tagihan pelanggan selama berlangganan.                                                 |
| **Churn**                  | Apakah pelanggan berhenti berlangganan (`Yes`) atau tetap (`No`). |


## Tujuan
1. Mengidentifikasi karakteristik pelanggan yang churn (berhenti) dan tidak churn.
2. Menganalisis hubungan antara durasi langganan (tenure), metode pembayaran, layanan yang digunakan, dan biaya bulanan dengan keputusan pelanggan untuk berhenti.

### Distribusi Churn
![Image](https://github.com/user-attachments/assets/8269187a-7a3f-41d7-95cf-9f63617d6f5b)
Grafik ini menunjukkan bahwa sekitar 73% pelanggan tetap berlangganan, sedangkan 27% berhenti (churn).
Angka churn ini penting sebagai tolak ukur kesehatan pelanggan. Jika tren ini meningkat, perusahaan perlu memperkuat strategi retensi pelanggan.

### Rata-rata bulanan berdasarkan status churn
![Image](https://github.com/user-attachments/assets/931c3b0a-c28f-421b-859d-ffd440b11408)
Pelanggan yang churn memiliki rata-rata biaya bulanan lebih tinggi dibanding pelanggan yang bertahan.
Hal ini mengindikasikan bahwa pelanggan dengan pengeluaran tinggi mungkin merasa tidak sebanding antara biaya dan manfaat layanan, atau memiliki ekspektasi lebih tinggi terhadap layanan.

### Persentase churn berdasarkan gender
![Image](https://github.com/user-attachments/assets/d87789c8-44d9-4b86-9b11-632bcb765442)
Grafik ini membandingkan proporsi churn antara pelanggan laki-laki dan perempuan. Tingkat churn untuk pelanggan laki-laki (26.20%) dan perempuan (26.96%) sangat mirip. Artinya, gender bukanlah faktor yang signifikan dalam memengaruhi keputusan pelanggan untuk churn dalam dataset ini.



### Status churn berdasarkan kelompok lama berlangganan
![Image](https://github.com/user-attachments/assets/258e5c0e-3497-4793-9916-1d6ee0859b81)
Pelanggan baru (dengan masa langganan <12 bulan) memiliki tingkat churn paling tinggi. Sebaliknya, pelanggan menengah dan lama cenderung lebih loyal. Hal ini menunjukkan pentingnya strategi onboarding yang kuat dan pengalaman awal pelanggan yang baik untuk mengurangi churn dini.

### Proporsi churn berdasarkan jenis layanan internet
![Image](https://github.com/user-attachments/assets/c7707575-36f5-48b8-a8ca-ad254a3233f8)
Grafik ini menunjukkan persentase pelanggan yang churn (berhenti berlangganan) dibandingkan yang tetap, berdasarkan jenis layanan internet yang digunakan. Pelanggan DSL memiliki tingkat churn rendah (19%), menunjukkan mereka lebih cenderung bertahan. Pelanggan Fiber optic memiliki churn yang lebih tinggi (41.89%), menandakan potensi risiko kehilangan pelanggan lebih besar di segmen ini. Pelanggan tanpa layanan internet memiliki churn terendah (7.43%), kemungkinan karena kebutuhan mereka lebih sedikit dan loyalitas lebih tinggi.


### Jumlah pelanggan berdasarkan jenis kontak
![Image](https://github.com/user-attachments/assets/a271ed78-6089-4758-8b29-7842a2ba252d)
Mayoritas pelanggan (3.875 pelanggan) menggunakan kontrak month-to-month, yang mencerminkan fleksibilitas tinggi tetapi juga potensi churn yang lebih besar, karena pelanggan lebih bebas untuk berhenti kapan saja. Hanya sebagian kecil yang menggunakan kontrak 1 tahun (1.472 pelanggan) dan 2 tahun (1.685 pelanggan), yang berarti pelanggan dengan komitmen jangka panjang lebih sedikit.

## Business Insights
---
1. Tingkat Churn Cukup Tinggi (26.6%): Hampir 1 dari 4 pelanggan berhenti menggunakan layanan, ini menunjukkan adanya tantangan dalam mempertahankan pelanggan, terutama pada tahap awal langganan.

2. Pelanggan Baru Lebih Rentan Churn: Tingkat churn tertinggi terjadi pada pelanggan dengan masa langganan di bawah 12 bulan. Ini menunjukkan bahwa fase awal pengalaman pelanggan sangat krusial.

3. Churn Lebih Tinggi pada Pelanggan dengan Biaya Bulanan Besar: Pelanggan yang mengeluarkan biaya bulanan lebih tinggi cenderung lebih mudah churn, kemungkinan karena mereka merasa layanan tidak sesuai dengan biaya yang dibayarkan.

4. Kontrak Bulanan Lebih Rentan Churn: Sebagian besar pelanggan menggunakan kontrak month-to-month, yang fleksibel tetapi memiliki tingkat churn tertinggi. Pelanggan dengan kontrak 1 atau 2 tahun menunjukkan loyalitas lebih tinggi.

5. Fiber Optic Memiliki Risiko Churn Lebih Tinggi: Meskipun fiber optic umumnya menawarkan kecepatan lebih tinggi, pelanggan dengan jenis layanan ini justru menunjukkan churn yang lebih tinggi dibanding DSL. Hal ini bisa menunjukkan adanya ketidakpuasan terhadap harga, kualitas, atau layanan pelanggan.

6. Gender Tidak Berpengaruh Signifikan: Perbedaan churn antara gender sangat kecil, sehingga gender bukanlah faktor utama yang memengaruhi churn.
