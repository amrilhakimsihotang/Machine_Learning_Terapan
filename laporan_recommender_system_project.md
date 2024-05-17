# Laporan Proyek Machine Learning - Amril Hakim Sihotang
## Project Overview
Proyek ini bertujuan untuk mengembangkan sistem rekomendasi berbasis konten untuk lagu-lagu teratas dari Spotify. Dengan menggunakan teknik *content-based filtering* dan *collaborative filtering*, sistem ini akan memberikan rekomendasi lagu kepada pengguna berdasarkan fitur-fitur dari lagu-lagu yang sebelumnya mereka dengar dan sukai. Dengan menganalisis atribut seperti nama lagu,*playlist* ,*streaming* dan artis. Tujuan utamanya adalah memberikan pengalaman mendengar musik yang disesuaikan dengan preferensi individual pengguna, memperkaya setiap sesi mendengar musik mereka dengan lagu-lagu yang relevan dan menarik.
## Latar Belakang
Dalam era digital saat ini, layanan streaming musik seperti Spotify telah menjadi bagian integral dari kehidupan sehari-hari banyak orang. Statistik penggunaan platform Spotify  di kuartal ke-3 tahun 2023<sup>[[1]](https://www.statista.com/statistics/653926/music-streaming-service-subscriber-share/)</sup> menunjukkan bahwa persentase pendengar musik secara global berkisar 31,7% untuk mendengarkan lagu favorit mereka. Namun, dengan begitu banyak pilihan lagu yang tersedia, pengguna sering kali menghadapi kesulitan dalam menemukan lagu-lagu baru yang sesuai dengan preferensi mereka. Hasil riset oleh Spotify juga menunjukkan bahwa rekomendasi lagu yang tepat dapat meningkatkan waktu yang dihabiskan pengguna di platform dan dapat meningkatkan kepuasan pengguna.

Sistem rekomendasi dapat dibangun dengan menggunakan teknik *content-based filtering* dan *collaborative filtering* Untuk memberikan rekomendasi yang relevan bagi pengguna. Penelitian telah menunjukkan bahwa pendekatan ini efektif dalam menyediakan rekomendasi yang lebih personal dan memuaskan kepada pengguna, karena menganalisis atribut-atribut lagu yang disukai oleh pengguna dan mempertimbangkan preferensi mereka.
## Business Understanding
Dalam industri *streaming* musik yang kompetitif, mempertahankan dan meningkatkan kepuasan pengguna merupakan kunci keberhasilan. Dengan menyediakan rekomendasi lagu yang relevan dan disesuaikan dengan preferensi pengguna, Spotify dapat meningkatkan keterlibatan pengguna, memperpanjang waktu dengar, dan meningkatkan retensi pelanggan. Selain itu, dengan meningkatnya jumlah lagu yang tersedia, sistem rekomendasi yang efektif juga dapat membantu menyoroti lagu-lagu baru dan kurang dikenal, memperluas audiens bagi artis dan label rekaman.
## Problem Statements
Masalah utama yang dihadapi pengguna Spotify adalah:
+ Bagaimana pengguna Spotify dapat dengan mudah menemukan lagu-lagu baru yang sesuai dengan preferensi mereka di antara jutaan lagu yang tersedia di platform?
+ Bagaimana Spotify dapat memberikan rekomendasi lagu yang lebih relevan untuk meningkatkan pengalaman mendengarkan musik pengguna?
+ Bagaimana cara meningkatkan retensi pengguna Spotify dengan memastikan mereka puas dalam menemukan lagu-lagu baru yang sesuai dengan preferensi mereka?
## Goals
Tujuan proyek ini adalah:
+ Mengembangkan sistem rekomendasi yang dapat memberikan rekomendasi lagu yang relevan dan sesuai dengan preferensi pengguna.
+ Meningkatkan kepuasan pengguna dengan menyediakan pengalaman mendengarkan musik yang lebih personal dan memuaskan.
+ Meningkatkan retensi pengguna dengan memberikan rekomendasi yang lebih akurat dan sesuai dengan preferensi mereka.
## Solution Statements
Solusi yang diusulkan adalah: 
+ Menggunakan teknik *content-based filtering* dan *collaborative filtering*, serta menerapkan pendekatan machine learning untuk menganalisis konten lagu dan terus belajar dari interaksi pengguna guna meningkatkan akurasi rekomendasi seiring waktu.
+ Mengumpulkan data dari histori mendengarkan pengguna untuk memahami preferensi mereka dan meningkatkan kepuasan pengguna.
+ Menganalisis atribut-atribut lagu yang disukai oleh pengguna untuk memberikan rekomendasi yang lebih personal dan relevan, sehingga meningkatkan retensi pengguna.   

## Data Understanding
Dataset yang digunakan pada proyek ini adalah **top-spotify-songs-2023**.
Adapun tabel informasinya sebagai berikut:

| Tipe                      | Deskripsi                                                                                         |
| ------------------------- | ------------------------------------------------------------------------------------------------- |
| Judul                     | Most Streamed Spotify Songs 2023                                                                  |
| Source                    | [top-spotify-songs-2023](https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023) |
| Author                    | NIDULA ELGIRIYEWITHANA                                                                            |
| Usability                 | 10.00                                                                                             |
| Expected update frequency | Annually                                                                                          |
| Visibility                | Public                                                                                            |
| Format                    | csv                                                                                               |

Tabel. 1. Informasi dataset yang digunakan.  
Dalam dataset tersebut memberikan informasi sebagai berikut:  
+ terdapat data sebanyak 953 baris
+ terdapat 24 kolom

Keterangan singkat untuk kolom yang ada sebagai berikut:  
+ track_name: Nama lagu.
+ artist(s)_name: Nama atau nama-nama artis yang terlibat dalam pembuatan lagu
+ artist_count: Jumlah artis yang terlibat dalam lagu tersebut.
+ released_year: Tahun rilis lagu.
+ released_month: Bulan rilis lagu.
+ released_day: Hari rilis lagu.
+ in_spotify_playlists: Indikasi apakah lagu tersebut termasuk dalam daftar putar di Spotify.
+ in_spotify_charts: Indikasi apakah lagu tersebut masuk dalam tangga lagu Spotify
+ streams: Jumlah stream atau putaran lagu yang telah diputar.
+ in_apple_playlists: Indikasi apakah lagu tersebut termasuk dalam daftar putar di Apple Music.
+ in_apple_charts: Indikasi apakah lagu tersebut masuk dalam tangga lagu Apple Music
+ in_deezer_playlists: Indikasi apakah lagu tersebut termasuk dalam daftar putar di Deezer.
+ in_deezer_charts: Indikasi apakah lagu tersebut masuk dalam tangga lagu Deezer
+ in_shazam_charts: Indikasi apakah lagu tersebut masuk dalam tangga lagu Shazam.
+ bpm: Beat per menit, menggambarkan kecepatan lagu.
+ key: Kunci musik atau kunci nada yang digunakan dalam lagu.
+ mode: Modus musik, bisa berupa mayor atau minor.
+ danceability_%: Persentase tingkat "danceability" atau kemampuan lagu untuk mengundang gerakan tari.
+ valence_%: Persentase tingkat "valence" atau tingkat kebahagiaan yang terpancar dari lagu.
+ energy_%: Persentase tingkat energi yang terdapat dalam lagu.
+ acousticness_%: Persentase tingkat akustik dalam lagu.
+ instrumentalness_%: Persentase tingkat instrumen dalam lagu.
+ liveness_%: Persentase tingkat "liveness" atau tingkat kesan rekaman langsung dalam lagu.
+ speechiness_%: Persentase tingkat "speechiness" atau seberapa banyak elemen pidato ada dalam lagu, misalnya rap   
   
Dengan memahami setiap variabel ini, analisis lebih lanjut tentang tren musik, preferensi pengguna, dan pengaruhnya terhadap popularitas lagu dapat dieksplorasi, memungkinkan pengembangan rekomendasi sistem yang lebih akurat dan relevan.  

#### Data visualiation
![Screenshot from 2024-05-14 14-42-10](https://github.com/amrilhakimsihotang/Machine_Learning_Terapan/assets/68908992/0e9fe1c3-5e25-4a94-999c-072ff477fa50)  
Gambar 1. Visualisasi data  


Grafik di atas menunjukkan peringkat lagu-lagu dalam bentuk Spotify Charts. Peringkat ini merupakan indikator popularitas relatif dari setiap lagu dalam rentang waktu tertentu. Dengan melihat grafik ini, dapat dipahami lagu-lagu mana yang sedang mendapat perhatian tinggi dari pendengar Spotify. Berdasarkan grafik tersebut dapat diamati **tren umum** diantaranya beberapa lagu yang sama nilai spotify charts seperti contoh lagu **Ella Baila Sola** dan **WHERE SHE GOES**. 

| #   | track_name                | in_spotify_charts |
| --- | ------------------------- | ----------------- |
| 0   | SevenfeatLattoExplicitVer | 147               |
| 1   | LALA                      | 48                |
| 2   | vampire                   | 113               |
| 3   | CruelSummer               | 100               |
| 4   | WHERESHEGOES              | 50                |
| 5   | Sprinter                  | 91                |
| 6   | EllaBailaSola             | 50                |
| 7   | Columbia                  | 43                |
| 8   | fukumean                  | 83                |
| 9   | LaBebeRemix               | 44                |

Tabel 2. Menampilkan peringkat lagu-lagu menggunakan fitur Spotify Charts  

Dan visualisasi grafik tersebut dapat dijadikan salah satu panduan berharga dalam memahami tren musik yang sedang berlangsung berdasarkan fitur **in_spotify_charts** dan juga dapat menjadi dasar untuk pengembangan sistem rekomendasi musik yang lebih baik.  



### Exploratory Data Analysis (EDA)
Sebelum lebih lanjut dalam hal proses data, tahapan selanjutnya adalah mengeksplor data untuk melihat keadaan data primer seperti:
+ Deskripsi Variabel  
    | #   | Column               | Non-Null Count           | Dtype  |
    | --- | -------------------- | ------------------------ | ------ |
    | 0   | track_name           | 953             non-null | object |
    | 1   | artist(s)_name       | 953             non-null | object |
    | 2   | artist_count         | 953             non-null | int64  |
    | 3   | released_year        | 953             non-null | int64  |
    | 4   | released_month       | 953             non-null | int64  |
    | 5   | released_day         | 953             non-null | int64  |
    | 6   | in_spotify_playlists | 953             non-null | int64  |
    | 7   | in_spotify_charts    | 953             non-null | int64  |
    | 8   | streams              | 953             non-null | object |
    | 9   | in_apple_playlists   | 953             non-null | int64  |
    | 10  | in_apple_charts      | 953             non-null | int64  |
    | 11  | in_deezer_playlists  | 953             non-null | object |
    | 12  | in_deezer_charts     | 953             non-null | int64  |
    | 13  | in_shazam_charts     | 903             non-null | object |
    | 14  | bpm                  | 953             non-null | int64  |
    | 15  | key                  | 858             non-null | object |
    | 16  | mode                 | 953             non-null | object |
    | 17  | danceability_%       | 953             non-null | int64  |
    | 18  | valence_%            | 953             non-null | int64  |
    | 19  | energy_%             | 953             non-null | int64  |
    | 20  | acousticness_%       | 953             non-null | int64  |
    | 21  | instrumentalness_%   | 953             non-null | int64  |
    | 22  | liveness_%           | 953             non-null | int64  |
    | 23  | speechiness_%        | 953             non-null | int64  |

    dtypes: int64(17), object(7)  
    memory usage: 178.8+ KB  
    Tabel 3. top_songs.info()  

+ Menangani *missing value*  
  Untuk menangani *missing value* pada tabel 2 (in_shazam_charts dan key),Secara umum ada dua cara untuk menangani *missing value* ini, yakni menghapusnya atau mengganti dengan nilai lain. untuk proyek ini, teknik yang digunakan adalah menghapus nilai yang hilang tersebut menggunakan metode dropna().  

    | #   | Column               | Non-Null Count           | Dtype  |
    | --- | -------------------- | ------------------------ | ------ |
    | 0   | track_name           | 953             non-null | object |
    | 1   | artist(s)_name       | 953             non-null | object |
    | 2   | artist_count         | 953             non-null | int64  |
    | 3   | released_year        | 953             non-null | int64  |
    | 4   | released_month       | 953             non-null | int64  |
    | 5   | released_day         | 953             non-null | int64  |
    | 6   | in_spotify_playlists | 953             non-null | int64  |
    | 7   | in_spotify_charts    | 953             non-null | int64  |
    | 8   | streams              | 953             non-null | object |
    | 9   | in_apple_playlists   | 953             non-null | int64  |
    | 10  | in_apple_charts      | 953             non-null | int64  |
    | 11  | in_deezer_playlists  | 953             non-null | object |
    | 12  | in_deezer_charts     | 953             non-null | int64  |
    | 13  | bpm                  | 953             non-null | int64  |
    | 14  | mode                 | 953             non-null | object |
    | 15  | danceability_%       | 953             non-null | int64  |
    | 16  | valence_%            | 953             non-null | int64  |
    | 17  | energy_%             | 953             non-null | int64  |
    | 18  | acousticness_%       | 953             non-null | int64  |
    | 19  | instrumentalness_%   | 953             non-null | int64  |
    | 20  | liveness_%           | 953             non-null | int64  |
    | 21  | speechiness_%        | 953             non-null | int64  |

    dtypes: int64(17), object(5)   
    memory usage: 163.9+ KB    
    Tabel 4. Hasil top_songs.info() setelah dilakukan penghapusan

## Data Preparation   
#### Content-Based Filtering  
Tahapan ini,akan dihapus beberapa kolom yang tidak diperlukan untuk membuat model untuk menghindari kegagalan dalam melakukan pelatihan.  
+ kolom yang tidak diperlukan adalah:  
   + artist_count
   + released_year, released_month, released_day
   + in_apple_playlists, in_apple_charts, 
   + in_deezer_playlists, in_deezer_charts, 
   + mode  
  
+ kemudian menghapus duplikat data pada dataset top_songs.
+ Menghapus karakter dan angka untuk kolom track_name
+ mengkonversi nilai streams menjadi int64.
+ Menyamakan track name di dataset spotify dan mendapatkan kumpulan nama lagu yang unik dari new_top_songs  
  
#### Collaborative Filtering   
Karena dataset yang digunakan adalah tunggal, maka perlu menggunakan pendekatan *implicit feedback* melalui jumlah streams di *playlist*, preferensi pengguna terhadap lagu tertentu dapat diketahui. adapun tahapan tersebut adalah:  
  + Menambahkan kolom song_id yang merefer ke kolom track_name
  + Menambahkan kolom user_id yang merefer ke kolom artist(s)_name 
  + Membuat one-hot encoding untuk kolom artist(s)_name

### Train-Test Split untuk Collaborative Filtering

Langkah penting dalam *Machine Learning* adalah pembagian dataset menjadi subset pelatihan dan pengujian. Tujuannya adalah untuk menguji kinerja model pada data yang tidak pernah dilihat sebelumnya. Dengan pembagian yang tepat, kinerja model dapat diukur secara objektif dan kegunaannya dapat dipastikan. Melihat jumlah dataset hanya berkisar dibawah 1000 data, maka proyek ini menggunakan rasio pembagian dataset **70:30**
## Modeling  
Pada proyek ini,akan menggunakan model *Content-Based Filtering* dan *Collaborative Filtering* sebagai pembanding hasil nantinya.  
 + *Content-Based Filtering*  
  *Content-based filtering* adalah metode yang merekomendasikan item kepada pengguna berdasarkan kemiripan item tersebut dengan item yang pernah disukai atau diakses oleh pengguna sebelumnya. Teknik ini menggunakan informasi yang ada pada konten item, seperti nama lagu, kata kunci, atau fitur lainnya, untuk menentukan kemiripan antara item.  
   + Kelebihan:
       + *Personalization*: Rekomendasi sangat spesifik terhadap preferensi pengguna.
       + *Cold Start Problem for Users*: Tidak ada masalah besar jika pengguna baru karena rekomendasi dapat segera diberikan berdasarkan preferensi awal pengguna.
       + *Interpretability*: Rekomendasi dapat dijelaskan karena didasarkan pada fitur konten yang jelas.
   + Kekurangan:
      + *Feature Engineering*: Membutuhkan ekstraksi fitur yang baik dari item, yang bisa kompleks dan memerlukan domain knowledge.
      + *Narrow Perspective*: Cenderung merekomendasikan item serupa, sehingga sulit untuk mengeksplorasi atau merekomendasikan item yang sangat berbeda dari yang pernah diakses.
      + *Cold Start Problem for Items*: Item baru tanpa deskripsi lengkap atau fitur yang teridentifikasi mungkin tidak direkomendasikan.  
  
   + Penggunaan Terbaik:  
Cocok digunakan pada sistem rekomendasi di mana deskripsi item jelas dan terstruktur, seperti artikel, musik, atau produk dengan atribut yang spesifik.  

    + Proses dan Tahapan Modeling:
      + Inisialisasi TfidfVectorizer:  
      Langkah pertama adalah menginisialisasi objek TfidfVectorizer, yang akan digunakan untuk mengubah teks dari track_name menjadi representasi numerik berdasarkan Term Frequency-Inverse Document Frequency (TF-IDF).

    + Perhitungan IDF:
      + Setelah itu, dilakukan perhitungan Inverse Document Frequency (IDF) pada data track_name. Proses ini menilai seberapa penting suatu kata dalam keseluruhan data.

    + Transformasi ke Matrix TF-IDF:
      + Data track_name kemudian diubah menjadi matrix TF-IDF. Setiap lagu diwakili oleh vektor yang menggambarkan pentingnya kata-kata dalam judul lagu tersebut.

    + Melihat Ukuran dan Isi Matrix TF-IDF:
      + Matrix TF-IDF yang terbentuk memiliki ukuran tertentu yang menunjukkan jumlah lagu dan jumlah fitur (kata unik). Isi dari matrix ini juga bisa dilihat untuk memahami representasi numerik dari data teks.

    + Menghitung Cosine Similarity:
      + Selanjutnya, dihitung cosine similarity antara vektor-vektor TF-IDF. Cosine similarity mengukur kesamaan antara dua vektor dalam ruang multidimensi, yang dalam konteks ini berarti seberapa mirip dua lagu berdasarkan judulnya.

    + Membuat DataFrame dari Cosine Similarity:
      + Hasil perhitungan cosine similarity kemudian diubah menjadi DataFrame. DataFrame ini memiliki indeks dan kolom berupa track_name, sehingga mudah untuk melihat kesamaan antara lagu-lagu.

    + Melihat Hasil Similarity Matrix:
     + Hasil similarity matrix dapat dilihat untuk memahami sejauh mana setiap lagu mirip dengan lagu lainnya. Ini bisa membantu dalam melakukan analisis lebih lanjut atau debugging.

    + Fungsi Rekomendasi Musik:
      + Sebuah fungsi dibuat untuk merekomendasikan musik berdasarkan judul lagu yang diberikan. Fungsi ini menggunakan similarity matrix untuk menemukan lagu-lagu yang paling mirip dengan lagu yang dicari.

    + Contoh Penggunaan Fungsi Rekomendasi:
      + Sebagai contoh, untuk merekomendasikan lagu-lagu yang mirip dengan lagu berjudul 'LALA', fungsi rekomendasi akan mencari dan menampilkan lagu-lagu dengan cosine similarity tertinggi terhadap 'LALA'.    

    + *Top N recomendation content based filtering*:  
      + *Content-based filtering* merekomendasikan item berdasarkan kemiripan konten dari item yang disukai oleh pengguna dengan item lainnya. Dalam kasus ini, TF-IDF digunakan untuk menghitung kesamaan judul lagu.

        + Proses *Top N Recommendation* dengan *Content-Based Filtering*:

          + *TF-IDF Vectorization*: Mengubah judul lagu menjadi vektor numerik menggunakan TF-IDF.
          + *Cosine Similarity*: Menghitung kesamaan antar lagu berdasarkan vektor TF-IDF.
          + *Retrieve Top N*: Mengambil N lagu teratas yang paling mirip dengan lagu yang dicari.  
        + Contoh Hasil *Content-Based Filtering*:   
          Ketika menjalankan *music_recommendations('LALA')*, sistem akan memberikan tabel rekomendasi seperti berikut:   
Disaat menjalankan *music_recommendations('LALA')* akan tampil tabel seperti dibawah ini.

| #   | track_name                   | artist(s)_name             | in_spotify_playlists | streams   |
| --- | ---------------------------- | -------------------------- | -------------------- | --------- |
| 0   | If We Ever Broke Up          | Mae Stephens               | 2040                 | 165584767 |
| 1   | Dijeron Que No La Iba Lograr | Fuerza Regida, Chino Pacas | 320                  | 116334601 |
| 2   | Something in the Orange      | Zach Bryan                 | 3282                 | 449701773 |
| 3   | Midnight Rain                | Taylor Swift               | 2612                 | 433356509 |
| 4   | VOID                         | Melanie Martinez           | 596                  | 67070410  |


Tabel 5. hasil prediksi *content-based filtering*  

Pada tabel diatas,sistem merekomendasikan kepada pengguna lagu berindeks-0 yang menempati urutan pertama di playlist **Spotify**, dan diikuti indeks lagu selanjutnya.   

+ *Collaborative Filtering*    
  *Collaborative filtering* adalah metode yang merekomendasikan item kepada pengguna berdasarkan kesamaan preferensi antar pengguna atau kesamaan antara item yang diakses oleh pengguna lain. Metode ini menggunakan data interaksi pengguna seperti pencarian nama lagu atau nama artis. 
   + Kelebihan:
     + *Discovering New Interests*: Dapat merekomendasikan item yang berbeda dari yang biasanya disukai pengguna, membantu dalam eksplorasi.
     + *Simplicity*: Implementasi lebih sederhana untuk berbagai jenis data tanpa memerlukan *domain knowledge* yang mendalam.
     + *Effectiveness*: Sangat efektif dalam banyak kasus karena memanfaatkan wisdom of the crowd.
  + Kekurangan:
    + *Cold Start Problem*: Kesulitan dalam memberikan rekomendasi untuk pengguna baru atau item baru tanpa banyak interaksi.
    + *Data Sparsity*: Kinerja dapat menurun jika data interaksi pengguna-item sangat jarang
    + *Scalability*: Mungkin membutuhkan sumber daya komputasi yang besar jika jumlah pengguna dan item sangat banyak. 
   
  + Penggunaan Terbaik:  
  Cocok digunakan dalam lingkungan di mana terdapat data interaksi pengguna-item yang besar, seperti e-commerce, streaming layanan musik dan video, atau platform media sosial.

  + Proses dan Tahapan Modeling: 
    + *Data Collection*: Mengumpulkan data interaksi pengguna dengan item,untuk kasus ini indikator yang digunakan adalah data streams dan pengguna disini adalah artis(s)_name.
    + *Data Preprocessing*: Membersihkan dan menyiapkan data untuk analisis.
    + Inisialisasi Model:  
      + Mendefinisikan kelas RecommenderNet yang merupakan turunan dari tf.keras.Model
      + Menentukan jumlah pengguna (num_users), jumlah lagu (num_songs), dan *embedding_size* untuk representasi vektor pengguna dan lagu.
      + Membuat *layer embedding* untuk pengguna dan lagu, serta layer bias untuk pengguna dan lagu.
      + Mengimplementasikan metode *call* yang mengambil input dan melakukan pemetaan vektor pengguna dan lagu, serta perhitungan prediksi.

    + Inisialisasi Model dan Kompilasi:
      + Menginisialisasi model dengan parameter yang telah ditentukan.
      + Mengompilasi model dengan fungsi loss menggunakan *Binary Crossentropy, optimizer Adam* dengan *learning rate* 0.001, dan metrik evaluasi *Root Mean Squared Error (RMSE)*.
    + Proses Training:
      + Melakukan proses training model dengan memanggil metode fit.
      + Menggunakan data training (x_train dan y_train).
      + Menggunakan *batch size* 8 dan jumlah epoch 100.
      + Melakukan validasi menggunakan data validasi (x_val dan y_val).  
    + *Top N recomendation Collaborative Filtering*:
      + *Collaborative filtering* merekomendasikan item berdasarkan kesamaan preferensi antar pengguna. Model ini mengasumsikan bahwa jika pengguna A menyukai item X, dan pengguna B memiliki kesukaan yang mirip dengan pengguna A, maka kemungkinan besar pengguna B juga akan menyukai item X.

      + Proses *Top N Recommendation* dengan *Collaborative Filtering*:
         + *User-Item Interaction Matrix*: Membuat matriks interaksi antara pengguna dan item (lagu).
         + *Model Training*: Melatih model collaborative filtering pada data interaksi pengguna-item.
         + *Retrieve Top N*: Mengambil N lagu teratas yang direkomendasikan untuk pengguna berdasarkan pola interaksi sebelumnya.
      + Contoh Hasil *Collaborative Filtering*:  
        Disaat menjalankan rekomendasi lagu dengan user id = 4, sistem akan memberikan tabel rekomendasi seperti berikut:  

    30/30 [==============================] - 0s 1ms/step  
Rekomendasi lagu untuk user_id 4:  

| song_id | track_name                | artist(s)_name            | in_spotify_playlists | streams    |
| ------- | ------------------------- | ------------------------- | -------------------- | ---------- |
| 1       | SevenfeatLattoExplicitVer | Latto, Jung Kook          | 553                  | 141381703  |
| 473     | Antidepresan              | Mabel Matiz, Mert Demir   | 313                  | 136689549  |
| 826     | Satellite                 | Harry Styles              | 3291                 | 311482393  |
| 620     | TheRumblingTVSize         | SiM                       | 254                  | 71014967   |
| 154     | NossoQuadro               | Ana Castela, AgroPlay     | 894                  | 233801632  |
| 16      | KillBill                  | SZA                       | 8109                 | 1163093654 |
| 750     | StillLife                 | BIGBANG                   | 181                  | 53909146   |
| 194     | ShutupMyMomsCalling       | Hotel Ugly                | 1788                 | 405136812  |
| 557     | pushinPfeatYoungThug      | Young Thug, Future, Gunna | 3517                 | 311395144  |
| 516     | SurfacePressure           | Jessica Darrow            | 1756                 | 267758538  |


Tabel 6. hasil rekomendasi collaborative filtering
       
## Evaluation

Model ***Content-Based Filtering*** yang diimplementasikan dalam skrip tersebut, menggunakan konsep perhitungan TF-IDF<sup>[[2]](https://en.wikipedia.org/wiki/Tf%E2%80%93idf)</sup> dan formula untuk menghitung *cosine similarity* antara dua vektor. *Content-Based Filtering* Didefinisikan dalam persamaan berikut ini<sup>[[3]](https://en.wikipedia.org/wiki/Cosine_similarity)</sup>:  


$$ Cosine Similarity: Sim(u₁, u₂) = \frac{A * B}{|A || B|}=\frac{\sum_{i=1}^n A_iB_i}{\sqrt{\sum_{i=1}^n A^²_i} * \sum_{i=1}^n B^²_i} $$


Dimana:
+ $A_i$ dan $B_i$ adalah komponen ke-i dari vektor A dan B.
+ A•B adalah hasil dari perkalian titik (dot product) antara vektor A dan B.
+ ∣∣A∣∣ dan ∣∣B∣∣ adalah panjang dari vektor A dan B, masing-masing.

Melihat dari tabel 4, dapat dihitung precision untuk model ini dengan rumus:  
$$ Precision = \frac{of our recommendation that are relevant}{of items we recommended} $$  

dimana:  
Precission adalah rekomendasi sistem  
*of our recommendation that are relevant* adalah rekomendasi yang relevan  
*of items we recommended* adalah item yang direkomendasikan  

| #   | track_name                   | artist(s)_name             | in_spotify_playlists | streams   |
| --- | ---------------------------- | -------------------------- | -------------------- | --------- |
| 0   | If We Ever Broke Up          | Mae Stephens               | 2040                 | 165584767 |
| 1   | Dijeron Que No La Iba Lograr | Fuerza Regida, Chino Pacas | 320                  | 116334601 |
| 2   | Something in the Orange      | Zach Bryan                 | 3282                 | 449701773 |
| 3   | Midnight Rain                | Taylor Swift               | 2612                 | 433356509 |
| 4   | VOID                         | Melanie Martinez           | 596                  | 67070410  |


Tabel 7. Hasil prediksi lagu *content-based filtering*   

Untuk menentukan relevansi lagu yang digunakan dalam proyek ini,salah satu pendekatan yang digunakan adalah **Popularitas (jumlah streams)**: Lagu dengan jumlah streams yang tinggi diasumsikan lebih relevan karena lebih banyak disukai oleh pendengar. Threshold yang digunakan dalam konteks ini adalah jumlah **minimum streams** untuk sebuah lagu agar dianggap populer dan relevan. Sebagai contoh, threshold dapat ditetapkan pada 100 juta streams. Lagu yang memiliki jumlah streams di atas threshold ini akan dianggap populer dan relevan.


Pertama, dapat dilihat bahwa ada 3 lagu teratas berdasarkan jumlah stream:  
  + Something in the Orange - Zach Bryan (449,701,773 streams)
  + Midnight Rain - Taylor Swift (433,356,509 streams)
  + If We Ever Broke Up - Mae Stephens (165,584,767 streams)


List lagu hasil prediksi yang didapat adalah:
 + If We Ever Broke Up - Mae Stephens
 +  Dijeron Que No La Iba Lograr - Fuerza Regida, Chino Pacas
 +  Something in the Orange - Zach Bryan
 +  Midnight Rain - Taylor Swift
 +  VOID - Melanie Martinez  

List yang teridentifikasi item yang relevan:
  + If We Ever Broke Up (relevan)
  + Dijeron Que No La Iba Lograr (tidak relevan)
  + Something in the Orange (relevan)
  + Midnight Rain (relevan)
  + VOID (tidak relevan)  
 
Ada 3 item yang relevan dari 5 item yang diambil.  
*Precision* dapat dihitung menggunakan rumus diatas yaitu: Precision = 3/5 = 0.6.  
Oleh karena itu, ketepatan rekomendasi berdasarkan streams adalah 0,6, atau 60%. Karena terdapat 5 lagu yang memiliki nilai streams di atas threshold maka didapatkan 60% precision dari model sistem rekomendasi dengan pendekatan content based filtering dan dianggap relevan berdasarkan jumlah streams.

  

Selanjutnya,model ***Collaborative Filtering*** yang diimplementasikan memiliki sebuah model RecommenderNet yang dikompilasi menggunakan *loss function Binary Crossentropy* dan *optimizer Adam* dengan *learning rate* 0.001. Metriks yang digunakan untuk evaluasi adalah *Root Mean Squared Error (RMSE)*. Model ini dilatih selama 100 epoch menggunakan data *training* dan validasi.  

Formula yang digunakan:  
+ *Binary Crossentropy Loss Function*:  
$$
Binary Crossentropy = -\frac{1}{N} \sum_{i=1}^{N} \left[ y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i) \right]
$$
dimana:  
*N* adalah jumlah sampel  
$y_i$ adalah nilai aktual sampel ke-i  
$\hat{y}_i$ adalah nilai prediksi sampel ke-i

+ *Adam Optimizer*  

​$$\theta_{t+1} = \theta_t - \frac{\eta}{\sqrt{v_t+\epsilon}} \cdot m_t$$  
dimana:  
$θ_t$ : parameter pada iterasi ke-t  
$η$: learning rate  
$m_ t$: estimasi momen pertama pada iterasi ke-t  
$v_t$ : estimasi momen kedua pada iterasi ke-t  
$ϵ$: nilai kecil untuk mencegah pembagian dengan nol

+ *Root Mean Squared Error (RMSE):*  
 $$\text{RMSE} = \sqrt{\frac{\sum_{i=1}^{N} (y_i - \hat{y_i})^2}{N}}$$  
dimana:  
*N* adalah jumlah sampel  
$y_i$ adalah label sebenarnya dari sampel ke-i  
$\hat{y}_i$ adalah prediksi model untuk sampel ke-i  

Dan hasil visualisasinya seperti gambar dibawah ini:  
![Screenshot from 2024-05-16 20-04-49](https://github.com/amrilhakimsihotang/Machine_Learning_Terapan/assets/68908992/3103684f-beb2-4621-a36a-e6763832b8e4)  
  
![Screenshot from 2024-05-16 20-05-48](https://github.com/amrilhakimsihotang/Machine_Learning_Terapan/assets/68908992/30acc7ba-8fc3-49fc-a7de-dbb56cd32b4a)
    

Gambar 2. Visualisasi metrik  *Loss Training* vs. *Loss Validation* dan *RMSE Training* vs. *RMSE Validation*    


Dapat disimpulkan bahwa pada grafik Loss dan RMSE, kedua metrik tersebut menurun seiring bertambahnya jumlah epoch, dan dipastikan bahwa perbedaan antara Loss dan RMSE pada data training dan data validasi tidak terlalu besar, yang menunjukkan bahwa model telah baik dalam melakukan generalisasi pada data yang belum pernah dilihat sebelumnya. Epoch terbaik dari hasil pelatihan ini adalah epoch ke-100, di mana model mencapai nilai **val_loss 0.0023** dan **val_root_mean_squared_error 0.0074**. Ini menunjukkan bahwa model memiliki kinerja terbaik dalam memprediksi data validasi pada epoch tersebut.  




## Referensi
[1]https://www.dicoding.com/academies/319/tutorials/17104  
[2]https://www.turing.com/kb/content-based-filtering-in-recommender-systems  
[3]https://developers.google.com/machine-learning/recommendation/collaborative/basics  
[4]https://en.wikipedia.org/wiki/Cosine_similarity    
[5]https://www.kaggle.com/
