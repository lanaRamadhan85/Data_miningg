# Adult Income Classification

Machine Learning project untuk mengklasifikasikan pendapatan seseorang (`<=50K` atau `>50K`) berdasarkan data demografis dan pekerjaan menggunakan Adult Census Income Dataset.

Project ini berfokus pada data preprocessing pipeline yang lengkap mulai dari data cleaning, encoding, splitting, hingga feature scaling.

---

## Dataset

Dataset yang digunakan adalah **Adult Census Income Dataset** dari:

* UCI Machine Learning Repository

Dataset terdiri dari:

* `adult.data`
* `adult.test`
* `adult.names`

Target variable:

* `income` → `<=50K` atau `>50K`

Jumlah data training setelah split:

* 26.048 data training
* 6.513 data testing
* Total fitur setelah encoding: 100 fitur

---

## Tech Stack

* Python 3
* NumPy
* Pandas
* Matplotlib
* Scikit-learn

---

## Project Workflow

### 1. Data Extraction

Dataset diekstrak dari file `.zip` menggunakan `zipfile`.

### 2. Data Loading

Dataset dibaca menggunakan `pandas.read_csv()` dengan penambahan custom column names karena file asli tidak memiliki header.

### 3. Handling Missing Values

Missing values diganti menggunakan:

```
SimpleImputer(strategy='most_frequent')
```

Strategi ini mengganti nilai kosong dengan nilai yang paling sering muncul (modus).

---

### 4. Encoding Categorical Features

Kolom kategorikal:

* workclass
* education
* marital-status
* occupation
* relationship
* race
* sex
* native-country

Metode:

* `ColumnTransformer`
* `OneHotEncoder(drop='first')`

Hasil:

* Dimensi fitur meningkat menjadi 100 kolom

---

### 5. Label Encoding

Target variable (`income`) diubah menjadi numerik:

* `<=50K` → 0
* `>50K` → 1

Menggunakan:

```
LabelEncoder()
```

---

### 6. Train-Test Split

Dataset dibagi menjadi:

* 80% Training
* 20% Testing

```
train_test_split(test_size=0.2, random_state=42)
```

---

### 7. Feature Scaling

Standarisasi fitur menggunakan:

```
StandardScaler()
```

Proses:

* Fit hanya pada training data
* Transform pada training dan testing data

Tujuan:

* Menyamakan skala fitur
* Menghindari bias akibat perbedaan magnitude antar fitur

---

## Final Data Shape

| Dataset | Shape        |
| ------- | ------------ |
| X_train | (26048, 100) |
| X_test  | (6513, 100)  |
| y_train | (26048,)     |
| y_test  | (6513,)      |

---

## Project Structure

```
adult-income-classification/
│
├── adult.zip
├── notebook.ipynb
├── README.md
└── requirements.txt
```

---

## Key Learning Outcomes

* Data preprocessing pipeline
* Handling missing values
* One-hot encoding categorical features
* Label encoding
* Feature scaling
* Data splitting strategy
* Preparing structured dataset for classification model

---

## Next Development

Project ini dapat dikembangkan lebih lanjut dengan:

* Logistic Regression
* Random Forest
* Support Vector Machine
* Model evaluation (Confusion Matrix, Accuracy, Precision, Recall, F1-score)
* Hyperparameter tuning
* Deployment menggunakan Flask / Streamlit

---

## Author

Lana Ramadhan

---

Kalau kamu mau, saya bisa tambahkan:

* Versi dengan model training + hasil accuracy
* Tambahkan badge GitHub (Python version, license, dll)
* Tambahkan section “How to Run”
* Tambahkan requirements.txt lengkap

Tinggal bilang mau dibuat untuk portfolio serius atau sekadar tugas kuliah.
