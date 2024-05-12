# Laporan Proyek Machine Learning - Amril Hakim Sihotang
## Domain Proyek
Dalam proyek ini, teknik machine learning digunakan untuk memprediksi harga emas, dengan tujuan membantu investor dalam pengambilan keputusan investasi yang lebih tepat. Algoritma dan metode *Machine Learning* yang digunakan akan dijelaskan, serta bagaimana hasil prediksi dapat memberikan kontribusi dalam menyelesaikan tantangan dalam pengambilan keputusan investasi di pasar emas.
### Latar Belakang
Harga<sup>[[1]](https://30rates.com/gold-price-forecast-and-predictions)</sup>  emas telah lama menjadi perhatian utama bagi para investor, pengamat ekonomi, dan pelaku pasar keuangan global. Emas dianggap sebagai salah satu instrumen investasi yang paling stabil dan sering digunakan sebagai lindung nilai terhadap inflasi dan ketidakstabilan ekonomi. Prediksi harga emas memainkan peran penting dalam menginformasikan keputusan investasi. Namun, karena banyak faktor yang memengaruhi harga emas, termasuk faktor ekonomi, geopolitik, sentimen pasar, dan volatilitas harga emas yang dapat dipengaruhi oleh faktor-faktor tersebut, memprediksi pergerakan harga emas dapat menjadi tugas yang kompleks<sup>[[2]](https://www.economies.com/commodities/gold-analysis)</sup>.

### Business Understanding
Dalam konteks prediksi harga emas untuk pengambilan keputusan investasi, pemahaman mendalam tentang dinamika pasar emas dan faktor-faktor yang memengaruhi pergerakan harga sangatlah penting. Namun, memprediksi pergerakan harga emas bukanlah tugas yang sederhana. Banyak faktor yang berkontribusi, seperti kondisi ekonomi, geopolitik, sentimen pasar, dan volatilitas harga yang dipengaruhi oleh variabel-variabel tersebut.

### Problem Statements

* Bagaimana mengatasi volatilitas harga emas yang tinggi dengan melakukan pendekatan Machine learning
* Bagaimana kompleksitas dalam memprediksi Pergerakan Harga Emas.
    

### Goals
Tujuan utama adalah:
* Memberikan gambaran prediksi harga emas dengan pendekatan *Machine Learning*
* Membantu para investor dalam melakukan transaksi jual beli emas.

### Solution Statements
Agar goal terpenuhi, solusi yang dapat dilakukan:
* Menganalisis data melalui analisis univariat dan multivariat. Selain itu, pemahaman data bisa diperoleh melalui visualisasi, yang membantu dalam mengidentifikasi matriks korelasi antar fitur serta outlier.
* Memastikan proses data cleaning dan standarisasi data dilakukan untuk memperoleh prediksi yang akurat.
* Membuat beberapa variasi model prediksi harga emas untuk pengambilan keputusan investasi dengan tujuan memperoleh model terbaik. Salah satu pendekatan yang digunakan adalah menciptakan variasi dalam parameter dan algoritma model, serta melakukan evaluasi terhadap kinerja masing-masing model seperti:
  + Algoritma K-Nearest Neighbor (KNN), 
  + Algoritma Random Forest, 
  + Algoritma Boosting(Adaptive Boosting),
  + Algoritma Linear Regression
  

### Data Understanding
Dataset yang digunakan pada proyek ini adalah Gold Price Archive 2010-2023\
Adapun tabel informasinya sebagai berikut:
| Tipe                      | Deskripsi                                                                                              |
| ------------------------- | ------------------------------------------------------------------------------------------------------ |
| Judul                     | Gold Price Archive 2010-2023 Dataset                                                                   |
| Source                    | [gold-price-kaggle](https://www.kaggle.com/datasets/ahmadkarrabi/gold-price-archive-2010-2023-dataset) |
| Author                    | AHMAD KARRABI                                                                                          |
| Visibility                | Public                                                                                                 |
| Usability                 | 10.00                                                                                                  |
| Expected update frequency | Annually                                                                                               |
| Format                    | csv                                                                                                    |



Dalam dataset tersebut memberikan informasi sebagai berikut:
* Terdapat data sebanyak 986004 baris.
* Terdapat 7 kolom yaitu time, open, high, low, close, rsil4, smal4

Keterangan fitur yang ada:
* *time*: *Timestamp* dari harga yang direkam. *Timestamp* ini penting karena memungkinkan untuk menganalisis perilaku harga dari waktu ke waktu, serta memungkinkan untuk melakukan analisis temporal seperti tren harian, mingguan, atau bulanan.
* *open*: Harga pembukaan adalah harga pertama pada periode tertentu, misalnya hari perdagangan. Ini adalah harga pertama yang diperdagangkan pada periode tersebut dan menunjukkan di mana pasar dibuka.
* *high*: harga tertinggi yang dicapai oleh aset selama periode waktu tertentu (misalnya, hari perdagangan). Ini memberikan wawasan tentang tingkat maksimum di mana aset diperdagangkan selama periode tersebut.
* *low*: Harga terendah yang dicapai oleh aset selama periode waktu tertentu (misalnya, hari perdagangan). Ini memberikan wawasan tentang tingkat minimum di mana aset diperdagangkan selama periode tersebut.
* *close*: Harga penutupan adalah harga terakhir yang diperdagangkan pada periode tertentu (misalnya, hari perdagangan). Ini menunjukkan di mana pasar ditutup pada periode tersebut dan memberikan informasi tentang sentimen pasar terakhir.
* rsi14: *Indeks Kekuatan Relatif (RSI)* adalah indikator teknis yang mengukur kekuatan dan kecepatan perubahan harga. RSI dihitung dengan membandingkan perbandingan antara total kenaikan harga dan total penurunan harga selama periode waktu tertentu.Nilai RSI14 mengacu pada RSI yang dihitung selama periode 14 hari.
* sma14: *Simple Moving Average (SMA)* adalah rata-rata harga tertentu selama periode waktu tertentu. SMA14 adalah rata-rata harga selama periode 14 hari.

Dengan memahami setiap variabel ini, analisis lebih lanjut tentang perilaku pasar dan potensi pola atau tren harga dapat dilakukan.

#### Exploratory Data Analysis
Sebelum lebih lanjut dalam hal proses data, tahapan selanjutnya adalah mengeksplor data untuk melihat keadaan data primer seperti mencari korelasi antar fitur, mencari *outlier*, analisis *univariate* dan *multivariate*.

* Info tabel *variable*\
  <class 'pandas.core.frame.DataFrame'><br>
   RangeIndex: 986004 entries, 0 to 986003<br>
   Data columns (total 7 columns):<br>
   | #   | Column | Non-Null | Count    | Dtype   |
   | --- | ------ | -------- | -------- | ------- |
   | 0   | time   | 986004   | non-null | object  |
   | 1   | open   | 986004   | non-null | float64 |
   | 2   | high   | 986004   | non-null | float64 |
   | 3   | low    | 986004   | non-null | float64 |
   | 4   | close  | 986004   | non-null | float64 |
   | 5   | rsi14  | 986004   | non-null | float64 |
   | 6   | sma14  | 986004   | non-null | float64 |
<br>
  dtypes: float64(6), object(1)
  memory usage: 52.7+ MB 

  Tabel 1. golds_data.info()

* Deskripsi *variable*

  |       | open          | high          | low           | close         | rsi14         | sma14         |
  | ----- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
  | count | 986004.000000 | 986004.000000 | 986004.000000 | 986004.000000 | 986004.000000 | 986004.000000 |
  | mean  | 1480.687806   | 1481.201203   | 1480.169858   | 1480.688379   | 50.260961     | 1480.681750   |
  | std   | 269.235947    | 269.360461    | 269.108012    | 269.235929    | 11.309953     | 269.230025    |
  | min   | 1046.920000   | 1048.080000   | 1044.180000   | 1046.940000   | 3.000000      | 1048.840000   |
  | 25%   | 1252.750000   | 1253.080000   | 1252.400000   | 1252.750000   | 42.810000     | 1252.740000   |
  | 50%   | 1373.580000   | 1374.180000   | 1373.055000   | 1373.580000   | 50.250000     | 1373.580000   |
  | 75%   | 1732.680000   | 1733.320000   | 1732.010000   | 1732.680000   | 57.730000     | 1732.660000   |
  | max   | 2138.000000   | 2145.140000   | 2125.980000   | 2138.410000   | 96.800000     | 2116.810000   |

   Tabel 2. golds_data.describe()
* Melihat *missing value*
  | time   | 0     |
  | ------ | ----- |
  | open   | 0     |
  | high   | 0     |
  | low    | 0     |
  | close  | 0     |
  | rsi14  | 0     |
  | sma14  | 0     |
  | dtype: | int64 |
  
  Tabel 3. Menampilkan jumlah nilai null dalam setiap kolom

  *Output* df pada gambar,menunjukkan tidak terdapat *missing values* di setiap kolom
* Pengamatan nilai pada *Outlier*\
  ![Screenshot from 2024-05-09 11-03-29](https://github.com/amrilhakimsihotang/Machine_Learning_Terapan/assets/68908992/2b9c3064-553d-45d8-998d-91bf8fe91cb2)\
  Gambar 1.Menampilkan *outlier* grafik
  
  Dari gambar 1 Tidak ada *outlier* yang terlihat. Untuk memastikannya, metode Z-score akan digunakan pada kolom sebagai contoh output.\
  **(986004,6)**\
 Identifikasi outlier menggunakan metode Z-score, dalam hal ini kolom time tidak diikutsertakan. 
 Metode lain untuk mengamati outlier adalah dengan menggunakan metode IQR. hasil *output* dari metode IQR:\
 **(976717,7)**



* *Univariate Analysis - Close*\
  Fitur yang akan diprediksi adalah fitur close
  ![Screenshot from 2024-05-09 11-07-00](https://github.com/amrilhakimsihotang/Machine_Learning_Terapan/assets/68908992/51df5f08-44fe-4b8c-a473-03190fe4f37d) 
  Gambar 2.Menampilkan *Univariate* Analysis grafik


* *Multivariate Analysis*
  ![download](https://github.com/amrilhakimsihotang/Machine_Learning_Terapan/assets/68908992/b4c21926-6701-4045-805b-5a10cb5667ac)
   Gambar 3.Menampilkan *Multivariate* Analysis grafik

   Melihat kolerasi fitur ***close*** terhadap fitur lain ***(open, high, low)***
dan terlihat, fitur ***close*** mempunyai dampak positif terhadap fitur lainnya.

* Kolerasi Matriks\
  Terlihat pada kolerasi matriks dibawah ini bahwa arah kolerasi bernilai positif.

  ![download](https://github.com/amrilhakimsihotang/Machine_Learning_Terapan/assets/68908992/0684f0f4-441e-4480-8990-6f420caab2d0)
  Gambar 4.Menampilkan kolerasi matriks
  

### Data Preparation
Tahapan ini,akan dihapus beberapa kolom yang tidak diperlukan menghindari masalah dalam pemrosesan data dan analisis. Teknik yang digunakan adalah:
* Menghapus kolom yang tidak diperlukan
  + Untuk menghapus kolom yang tidak diperlukan, dapat menggunakan metode ***drop*** dan kolom yang dihapus adalah "time", "rsi14","sma14"
* Menghapus nilai yang hilang
  + Metode yang dapat digunakan adalah dengan menggunakan *dropna()*. Tujuannya untuk menghapus baris yang memiliki nilai yang hilang (NaN).
* Menghapus data duplikat
  + Untuk mencegah data duplikat, dapat menggunakan metode *drop_duplicates()* dengan argumen.Bertujuan untuk menghapus baris yang memiliki nilai yang sama dengan baris lainnya.Hasil yang di dapat seperti tabel dibawah ini.
  
  |        | open    | high    | low     | close   |
  | ------ | ------- | ------- | ------- | ------- |
  | 1      | 1100.00 | 1100.30 | 1099.45 | 1099.75 |
  | 2      | 1099.70 | 1100.10 | 1099.30 | 1099.45 |
  | 3      | 1099.50 | 1099.60 | 1098.50 | 1099.45 |
  | 4      | 1099.40 | 1099.60 | 1098.90 | 1098.90 |
  | 5      | 1098.95 | 1099.20 | 1098.60 | 1098.90 |
  | ...    | ...     | ...     | ...     | ...     |
  | 985999 | 2063.07 | 2063.24 | 2062.60 | 2062.96 |
  | 986000 | 2062.95 | 2063.09 | 2062.52 | 2062.61 |
  | 986001 | 2062.60 | 2062.83 | 2062.34 | 2062.56 |
  | 986002 | 2062.56 | 2063.20 | 2062.51 | 2062.54 |
  | 986003 | 2062.52 | 2063.00 | 2062.37 | 2062.73 |
  976717 rows × 4 columns
  Tabel 4. Data Preparation

#### Train-Test Split
Langkah penting dalam *Machine Learning* adalah pembagian dataset menjadi subset pelatihan dan pengujian. Tujuannya adalah untuk menguji kinerja model pada data yang tidak pernah dilihat sebelumnya. Dengan pembagian yang tepat, kinerja model dapat diukur secara objektif dan kegunaannya dapat dipastikan. Pada proyek ini, rasio pembagian dataset adalah **80:20**.
#### Standarisasi
Tujuannya untuk menghindari kebocoran informasi data saat melakukan pengujian.
### Modeling
Pada proyek ini,akan menggunakan model *K-Nearest Neighbor,Random Forest,Boosting Algorithm* dan *Linear Regression* sebagai pembanding hasil nantinya.

* *K-Nearest Neighbor (KNN)* adalah algoritma yang digunakan untuk klasifikasi dan regresi. Ini bekerja dengan cara mencari kelas atau nilai target dari k-tetangga terdekat dari titik data yang akan diprediksi, berdasarkan pada metrik jarak seperti jarak Euclidean. KNN adalah algoritma non-parametrik, yang berarti tidak ada asumsi yang dibuat tentang distribusi data.
  * Kelebihan:
    * Tidak memerlukan asumsi tentang distribusi data.
    * Mudah diimplementasikan dan dipahami.
  * Kekurangan:
    * Rentan terhadap overfitting jika nilai K terlalu kecil.
    * Kinerja buruk pada dataset dengan dimensi yang tinggi.
  * Penggunaan Terbaik:
    * Klasifikasi pada dataset dengan sebaran data yang tidak teratur.
  * proses dan tahapan modeling yang dilakukan:

    * Proses: Menggunakan algoritma KNN untuk membuat model prediksi.
    * Tahapan: Menentukan jumlah tetangga terdekat (n_neighbors), dan melatih model menggunakan data latih (x_train_data, y_train_data).
    * Cara Kerja: Model KNN memprediksi nilai target berdasarkan mayoritas dari k tetangga terdekat dari titik yang akan diprediksi.


* *Random Forest* adalah salah satu algoritma machine learning yang digunakan untuk tugas-tugas klasifikasi dan regresi. Ini adalah jenis ensemble learning di mana sejumlah besar pohon keputusan (decision trees) digunakan saat pelatihan
  * Kelebihan:
    * Mampu menangani berbagai jenis data, termasuk data kategorikal dan numerik.
    * Mampu menangani overfitting dengan baik karena penggunaan banyak pohon keputusan.
  * Kekurangan:
    * Memiliki kompleksitas yang tinggi sehingga membutuhkan lebih banyak sumber daya komputasi dan waktu untuk melatih model.
    * Sulit untuk diinterpretasikan dibandingkan dengan model sederhana seperti regresi linear.
  * Penggunaan Terbaik:
    * Klasifikasi atau regresi pada dataset dengan fitur yang kompleks dan non-linier.
  * proses dan tahapan modeling yang dilakukan:
    * Proses: Membuat model menggunakan algoritma Random Forest.
    * Tahapan: Menentukan jumlah pohon (n_estimators), kedalaman maksimum (max_depth), dan variabel lainnya. Melatih model dengan data latih.
    * Cara Kerja: Random Forest membangun beberapa pohon keputusan dan menggabungkan hasil prediksi dari setiap pohon untuk memperoleh prediksi akhir.


* *Adaptive Boosting (Adaboost)* adalah salah satu metode dalam machine learning yang digunakan untuk meningkatkan performa model prediksi dengan cara mengkombinasikan beberapa model prediksi sederhana (weak learners) menjadi satu model yang kuat (strong learner). Prinsip utama dari Adaboost adalah memberikan bobot yang dinamis pada setiap instance/data training, sehingga model dapat fokus pada instance yang sulit diprediksi oleh model sebelumnya.
  * Kelebihan:
    * Mampu menangani data yang tidak seimbang dengan baik.
    * Tidak rentan terhadap overfitting karena menggunakan kombinasi model sederhana (misalnya, pohon keputusan yang dangkal).
  * Kekurangan:
    * Rentan terhadap noise dan outliers karena fokus pada kesalahan yang ada pada setiap iterasi.
    * Performa dapat menurun jika terdapat banyak noise atau outlier dalam data.
  * Penggunaan Terbaik:
    * Regresi pada dataset dengan struktur yang kompleks atau noise yang signifikan.
  * proses dan tahapan modeling yang dilakukan:
    * Proses: Menggunakan algoritma Boosting (dalam hal ini, AdaBoost) untuk pembuatan model.
    * Tahapan: Menentukan tingkat pembelajaran (learning_rate) dan melatih model dengan data latih.
    * Cara Kerja: Boosting memperkuat model dengan menfokuskan pada sampel yang sulit diprediksi sebelumnya.
* *Linear Regression* adalah metode dalam machine learning yang digunakan untuk memodelkan hubungan linier antara satu atau lebih variabel *input* (disebut juga prediktor, fitur, atau variabel independen) dengan variabel target (disebut juga variabel dependen). Tujuannya adalah untuk menemukan garis lurus yang paling baik memprediksi nilai target berdasarkan nilai-nilai *input* yang diberikan.
  * Kelebihan:
    * Mudah dipahami dan diinterpretasikan.
    * Cocok untuk masalah di mana hubungan antara variabel *input* dan *output* dapat dijelaskan secara linier.
  * Kekurangan:
    * Cenderung bekerja buruk jika hubungan antara variabel *input* dan *output* tidak linier.
    * Rentan terhadap outliers yang signifikan.
  * Penggunaan Terbaik:
    * Prediksi pada dataset dengan hubungan linier antara variabel *input* dan *output*
  * proses dan tahapan modeling yang dilakukan:
    * Proses: Membuat model menggunakan regresi linear.
    * Tahapan: Melatih model dengan data latih.
    * Cara Kerja: Linear Regression mencoba untuk menemukan hubungan linier antara variabel independen dan variabel target. 
    
Pada proyek ini menggunakan model *RandomForest(RF)* dikarenakan memiliki tingkat error hasil pelatihan sebesar 0.00007(gambar 12) yang sangat sedikit dari ketiga model lainnya.

### Evaluation
Untuk jenis metrik yang digunakan sebagai evaluasi adalah mse <i>(mean squared error).</i>
*MSE* didefinisikan dalam persamaan berikut<sup>[[3]](https://www.dicoding.com/academies/319/tutorials/18595)</sup> :

$$ MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 $$

dimana:\
n adalah jumlah sampel atau data.\
y<sub>i</sub> adalah Nilai yang diamati (nilai aktual) untuk sampel ke-i.\
y^<sub>i</sub> adalah nilai yang diprediksi untuk sampel ke-<i>i</i>


Hasil prediksi untuk ke empat model dapat dilihat hasilnya seperti tabel dibawah ini:
| y_true | prediksi_KNN | prediksi_RF | prediksi_Boosting | prediksi_LR |
| ------ | ------------ | ----------- | ----------------- | ----------- |
| 545465 | 1091.92      | 1092.4      | 1092.4            | 1133.9      | 1092.4 |

|          | train    | test     |
| -------- | -------- | -------- |
| KNN      | 0.000125 | 0.000152 |
| RF       | 0.00007  | 0.000152 |
| Boosting | 1.059026 | 1.060601 |
| LR       | 0.000134 | 0.000134 |


Tabel 5. nilai mse dan hasil prediksi dari keempat model

Dari hasil tersebut, dapat dilihat bahwa MSE untuk algoritma Boosting jauh lebih tinggi dibandingkan dengan yang lain baik pada data latih maupun data uji. Sedangkan untuk algoritma KNN, RF, dan LR, MSE pada data latih dan data uji hampir sama. Semakin kecil MSE, semakin baik performa modelnya. Berdasarkan tabel 5 diatas, model ***RandomForest(RF)*** menunjukkan performa terbaik dengan memiliki mse yang terendah untuk data pelatihan(train) dan hasil yang sebanding dengan *K-Nearest Neighbors (KNN) *untuk data uji(test).

## Refenrensi
[1]https://www.dicoding.com/academies/319/tutorials/16994<br>
[2]https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html
[3]https://www.analyticsvidhya.com/blog/2021/09/adaboost-algorithm-a-complete-guide-for-beginners
[4]https://www.kaggle.com/datasets/ahmadkarrabi/gold-price-archive-2010-2023-dataset
