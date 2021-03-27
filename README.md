# Dimensionality Reduction

Salah satu masalah yang sering terjadi dalam suatu machine learning adalah “Curse of Dimensionality problem”, di mana mesin kesulitan dalam menangani sejumlah masukan data dengan dimesi yang sangat tinggi. Salah satu cara yang paling umum digunakan untuk menangani proses ini adalah dengan mengurangi dimensi dari data masukan dengan tetap menjaga informasi yang terkandung didalamnya. 

Salah satu cara yang paling sering digunakan adalah PCA (Principal Component Analysis), karena PCA dapat mereduksi dimensi seminimal mungkin dengan tetap mempertahankan informasi yang terkandung di dalamnya.

## Algoritma
Beberapa teknik yang bisa digunakan untuk mengurangi dimensi yang cukup tinggi adalah
1. Ratio of missing values
2. Low variance in the column values
3. High correlation between two columns
4. Principal component analysis (PCA)
5. Candidates and split columns in a random forest
6. Backward feature elimination
7. Forward feature construction

## Feature Selection vs Dimensionality Reduction
Keduanya memiliki fungsi yang sama yaitu mereduksi dimensi, namun terdapat perbedaan yang cukup mendasar yaitu

```
Feature selection is simply selecting and excluding given features without changing them. Dimensionality reduction transforms features into a lower dimension.
```

## Refference
- https://towardsdatascience.com/feature-selection-and-dimensionality-reduction-f488d1a035de
- https://thenewstack.io/3-new-techniques-for-data-dimensionality-reduction-in-machine-learning/


