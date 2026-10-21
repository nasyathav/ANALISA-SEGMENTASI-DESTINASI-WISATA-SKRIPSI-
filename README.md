# ANALISA SEGMENTASI DESTINASI WISATA SKRIPSI
# Rumusan Masalah
1.	Bagaimana penerapan algoritma K-Means dalam melakukan segmentasi destinasi wisata di Kabupaten Semarang berdasarkan tingkat kunjungan dan pendapatan? 
2.	Bagaimana menentukan jumlah klaster (K) yang paling optimal dalam pengelompokan destinasi wisata di Kabupaten Semarang menggunakan Elbow Method?
3.	Bagaimana performa algoritma K-Means dalam melakukan segmentasi destinasi wisata tersebut berdasarkan pengujian Silhouette Coefficient dan Davies Bouldin Index?
4.	Bagaimana hasil pengelompokan destinasi wisata di Kabupaten Semarang berdasarkan karakteristik jumlah pengunjung dan pendapatan? 
5.	Bagaimana hasil segmentasi destinasi wisata dapat digunakan sebagai dasar dalam mendukung strategi pengembangan pariwisata di Kabupaten Semarang?
# Proses Cleaning
1.	Pemeriksaan dan Penghapusan Data Kosong (Missing Value): Data dievaluasi menggunakan fungsi df.isnull().sum(), yang menemukan 110 baris kosong (hilang) pada kolom 'Pendapatan'. Baris data yang tidak lengkap tersebut kemudian dibuang dari dataset menggunakan perintah df.dropna(). 
2.	Pembersihan Karakter Teks (Data Cleaning): Kolom 'Pendapatan', 'Nusantara', dan 'Mancanegara' awalnya memuat karakter teks yang membuat data tidak bisa dihitung, seperti "Rp", titik ("."), koma (","), dan tanda strip ("-"). Karakter-karakter tersebut dihilangkan, sementara tanda strip diganti menjadi angka "0". 
3.	Konversi Tipe Data: Setelah karakter teks dibersihkan, tipe data pada kolom 'Pendapatan', 'Nusantara', 'Mancanegara', dan 'Jumlah Pengunjung' diubah menjadi format angka pasti menggunakan fungsi pd.to_numeric() agar kompatibel dengan operasi matematis. 
4.	Pemilihan Fitur (Feature Selection): Dari seluruh kolom yang ada, program hanya memilih tiga atribut utama untuk digunakan dalam proses algoritma clustering, yaitu 'Tahun', 'Jumlah Pengunjung', dan 'Pendapatan'. 
5.	Normalisasi Skala Data (Min-Max Scaling): Rentang angka pada ketiga atribut terpilih sangat berbeda (misalnya, 'Tahun' berwujud angka ribuan kecil, sedangkan 'Pendapatan' mencapai skala miliaran). Fungsi MinMaxScaler() diterapkan untuk mengubah dan memampatkan seluruh nilai data tersebut ke dalam rentang seragam antara 0 hingga 1. Proses ini sangat penting dalam algoritma jarak seperti K-Means agar variabel bernilai raksasa ('Pendapatan') tidak mendominasi perhitungan bobot klaster.
# Insight & Rekomendasi
1. Algoritma clustering (K-Means) akan mengelompokkan data berdasarkan kedekatan karakteristiknya.
2. Setelah Anda mengetahui posisi dan karakteristik tiap cluster, merekomendasikan evaluasi pengembangan destinasi wisata.
