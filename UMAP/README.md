
# UMAP (Uniform Manifold Approximation and Projection) - Reduksi Dimensi

## Deskripsi
UMAP (Uniform Manifold Approximation and Projection) adalah teknik untuk mereduksi dimensi data sambil mempertahankan struktur topologi asli. Teknik ini sering digunakan dalam analisis data dan visualisasi, terutama ketika bekerja dengan data berdimensi tinggi.

## Cara Kerja
### 1. Dasar Teori <br>
UMAP mengasumsikan bahwa data yang ada berada dalam manifold (permukaan data) berdimensi lebih tinggi. UMAP mencoba untuk menangkap hubungan struktural antara titik-titik data tersebut pada dimensi yang lebih rendah. Hal ini dilakukan dengan mengidentifikasi kedekatan lokal antara titik-titik yang serupa dan kemudian memproyeksikan kedekatan tersebut ke dimensi yang lebih rendah.

Manifold: Sebuah ruang atau permukaan dengan dimensi lebih rendah yang menggambarkan data dalam dimensi lebih tinggi.

Keberlanjutan Topologi: UMAP mempertahankan struktur kedekatan data saat melakukan proyeksi ke dimensi yang lebih rendah. Artinya, titik yang dekat dalam dimensi tinggi akan tetap dekat setelah reduksi dimensi.

### 2. Langkah-langkah Kerja UMAP
#### a. Konstruksi Graf Keterhubungan
UMAP memulai dengan membangun sebuah graf yang mewakili hubungan antar titik data berdasarkan kedekatannya. Di sini, setiap titik data dihubungkan dengan titik lainnya yang paling mirip berdasarkan suatu metrik jarak (seperti Euclidean).

Proyeksi Keterhubungan Lokal: UMAP menentukan tetangga terdekat (neighbors) dari setiap titik berdasarkan jarak atau kesamaan fitur, dan membangun graf berdasarkan tetangga-tetangga tersebut.

Kesamaan Lokal: UMAP menggunakan fungsi kesamaan lokal (misalnya, distribusi Gaussian) untuk menilai kedekatan atau hubungan antar titik dalam data. Titik yang lebih dekat dalam dimensi tinggi akan memiliki kesamaan lebih besar.

#### b. Pemrograman dan Pembelajaran Manifold
Setelah graf terbentuk, UMAP kemudian mencoba untuk memetakan data dari dimensi tinggi ke dimensi yang lebih rendah dengan cara meminimalkan perbedaan antara graf yang terbentuk dalam dimensi tinggi dan dimensi yang lebih rendah.

Optimalisasi Proyeksi: UMAP menggunakan algoritma optimisasi berbasis teori graf untuk menemukan representasi terbaik dari data dalam dimensi yang lebih rendah. Ini dilakukan dengan mengoptimalkan perbedaan (loss function) antara graf pada ruang tinggi dan rendah.

Kekekalan Struktur Topologi: UMAP berusaha untuk mempertahankan hubungan yang paling penting, yaitu kedekatan antar titik yang serupa. Titik-titik yang berada dalam "neighborhood" yang sama akan tetap berdekatan setelah dimensi dikurangi.

#### c. Proyeksi ke Dimensi Lebih Rendah
UMAP menghasilkan peta data yang lebih rendah dengan dua atau lebih dimensi berdasarkan optimisasi yang dilakukan pada langkah sebelumnya. Hasil akhirnya adalah data yang bisa dipetakan ke dalam plot atau grafik 2D atau 3D.

### 3. Algoritma dan Kecepatan
Salah satu alasan UMAP menjadi sangat populer adalah kecepatan dan efisiensinya. UMAP menggunakan teknik seperti approximate nearest neighbors (ANN) untuk mempercepat konstruksi graf dan optimisasi. Dengan menggunakan struktur data yang efisien seperti k-d tree atau ball tree, UMAP dapat menangani data dalam skala besar dengan cukup cepat.

### 4. Parameter Utama dalam UMAP
Beberapa parameter penting yang memengaruhi cara kerja UMAP adalah:

- n_neighbors: Menentukan jumlah tetangga terdekat yang digunakan untuk membangun graf. Nilai yang lebih tinggi akan menghasilkan proyeksi yang lebih global, sementara nilai yang lebih rendah cenderung fokus pada struktur lokal.

- min_dist: Menentukan seberapa dekat titik dalam dimensi rendah dapat didekatkan. Nilai lebih tinggi akan menghasilkan proyeksi yang lebih tersebar, sementara nilai lebih rendah akan menghasilkan proyeksi yang lebih padat.

- n_components: Menentukan dimensi output yang diinginkan (misalnya 2 untuk visualisasi 2D, 3 untuk visualisasi 3D).

### 5. Keuntungan UMAP Dibandingkan dengan Teknik Lain
- t-SNE vs UMAP: UMAP lebih cepat dan lebih skalabel dibandingkan dengan t-SNE, terutama untuk dataset besar. Selain itu, UMAP mempertahankan lebih banyak struktur global, sementara t-SNE lebih fokus pada struktur lokal.

- Preservasi Struktur: UMAP cenderung lebih baik dalam menjaga hubungan antara titik-titik yang lebih jauh dalam data dibandingkan dengan teknik lain seperti PCA atau t-SNE.

### 6. Aplikasi UMAP
- Visualisasi Data: UMAP digunakan untuk visualisasi data berdimensi tinggi dengan mereduksi dimensi menjadi 2 atau 3.
- Clustering: UMAP dapat digunakan sebagai pra-pemrosesan untuk teknik klastering (misalnya, K-means) untuk menemukan pola dalam data.
- Pemodelan dan Pembelajaran Mesin: UMAP sering digunakan dalam pembelajaran mesin untuk mempercepat pelatihan model dengan mengurangi dimensi data.


## Keuntungan UMAP:
- Mempertahankan struktur lokal dan global data.
- Lebih cepat daripada teknik lain seperti t-SNE.
- Cocok untuk data berdimensi tinggi.
