# Non-Negative Matrix Factorization

## Definisi 
Metode ini termasuk dalam faktorisasi matriks yang merupakan proses pemecahan atau penguraian suatu matriks menjadi beberapa matriks. Beberapa metode yang bisa digunakan untuk pemecahan matriks ini adalah
1. Direct Approach
- LU
- Cholesky
- QR
2. Aproximation Approach
- Singular Value Decomposition (SVD)
- Non-Negative Matrix Factorization (NMF)

## Model matematis
Goal utama dari ini adalah menemukan matriks W yang memenuhi persamaan **V ~ WH** dimana 
- **V** merupakan matriks data awal yang berukuran m x n
- **W** merupakan matriks yang berukuran m x k 
- **H** merupakan matriks yang berukuran k x n

dimana m adalah banyaknya observasi, n adalah banyaknya variabel dan k adalah banyaknya komponen yang terbentuk.

Untuk menyelesaikan masalah NMF ada beberapa algoritma yang sering digunakan, diantaranya additive update algorithm, multiplicative update algorithm, alternating least square algorithm, dll.

## Perbedaan dengan PCA
Pada faktorisasi SVD terdapat kecendrungan nilai matriks yang merepresentasikan hubungan antara kata dan topik bernilai negatif, sehingga akan menyulitkan dalam hal intrerpretasi. Oleh karena itu digunakanlah NMF agar nilai matrix bernilai positif sehingga memudahkan interpretasi.

## Code
```
## Fitting Model
from sklearn.decomposition import NMF
import pandas as pd
import seaborn as sns

model = NMF(n_components=2, init='random', random_state=0, max_iter=50000)
W = model.fit_transform(X)
H = model.components_
```

## Refference
1. https://papers.nips.cc/paper/2000/file/f9d1152547c0bde01830b7e8bd60024c-Paper.pdf
2. https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.NMF.html\EKSTRAKSI 
3. https://docplayer.info/83510173-Analisis-dan-implementasi-metode-clustering-dan-non-negative-matrix-factorization-pada-peringkasan-multi-dokumen.html

