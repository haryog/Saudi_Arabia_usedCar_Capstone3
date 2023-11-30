# Saudi Arabia Used Car

![salesperson-putting-sale-plate-on-the-car-2021-10-13-20-23-56-utc copy](https://github.com/haryog/Saudi_Arabia_usedCar_Capstone3/assets/144018986/c4cd6828-61d3-47e7-a358-1cc263ad26b4)

## Context : 
Arab sebagai salah satu negara penghasil minyak terbesar di dunia membuat harga bahan bakar menjadi lebih murah. Murahnya bahan bakar ini membuat penggunaan kendaaran terutama mobil di Arab Saudi juga semakin tinggi. Tingginya penggunaan mobil ini tentu memicu permintaan pasar terhadap mobil juga semakin masif, terutama mobil bekas. Berdasarkan www.mordorintelligence.com, pasar mobil bekas di Arab Saudi mencapai nilai sebesar USD 4,91 miliar pada tahun 2021 dan diproyeksikan akan terus meningkat nilai hingga USD 8,69 miliar pada tahun 2027. Hal tesebut dilihat dari pertumbuhan CAGR (Compound Annual Growth Rate) yang terus mengalami peningkatan sebesar 7,36% dari hasil proyeksi.

Masifnya permintaan terhadap mobil bekas ini mendorong para pelaku bisnis dalam melahirkan platform online jual beli mobil bekas, misalnya seperti syarah.com. Dengan begitu pelanggan tentunya dapat memilih kriteria mobil yang mereka idamkan. Harga yang ditentukan pun harus sesuai dengan spesifikasi yang dimiliki oleh mobil. Banyaknya mobil bekas yang tersedia dengan beberapa spesifikasi tertentu, membuat penentuan harga mobil terbaik merupakan faktor krusial yang perlu diperhatikan. Penentuan harga terbaik ini diperlukan agar proses jual dan beli mobil bekas menjadi semakin mudah. Apabila harga terlalu tinggi mobil akan sulit terjual, sebaliknya apabila harga terlalu rendah keuntungan yang didapatkan akan lebih kecil. 

## Problem :
Dengan tingginya demand mobil bekas di Arab Saudi, penentuan harga mobil bekas merupakan tantangan yang perlu diatasi bagi syarah.com. Persaingan yang ketat juga membuat penentuan harga mobil bekas yang akurat dan kompetitif menjadi faktor penting untuk melakukan analisa overprice dan underprice dalam pemberian harga mobil bekas. Dengan banyaknya pilihan mobil dengan berbagai spesifikasi dan kondisi, diharapkan perusahaan memiliki model bisnis yang dapat menentukan harga mobil yang kompetitif di pasaran agar banyak pelanggan tertarik untuk membeli mobil pada perusahaan ini. Selain itu pelanggan juga mendapatkan pengalaman terbaik dalam mencari pilihan mobil yang diinginkan sesuai spesifikasi dan harganya. Kemudahan dan harga yang kompetitif inilah yang dapat meningkatkan jumlah pelanggan dan tentu saja meningkatkan pendapatan yang lebih maksimal.

## Goals :
Berdasarkan problem statement diatas, syarah.com harus memiliki tools yang dapat **memprediksi harga mobil bekas sesuai dengan kriteria** dan membantu pelanggan untuk menemukan mobil sesuai dengan apa yang diinginkan. Adapun kriteria-kriteria yang perlu diperhatikan dalam menentukan harga mobil bekas yakni, merk mobil, tipe mobil, gear type, asal mobil, tahun mobil, jarak tempuh, hingga engine size diharapkan dapat **memberikan akurasi yang baik dalam menentukan harga mobil**, yang mana dapat memberikan harga yang kompetitif di pasaran yang terjangkau bagi pelanggan namun tetap menguntungkan bagi perusahaan. Tidak hanya itu, dengan adanya `tool` machine learning ini diharapkan juga mampu memprediksi harga terbaik dengan lebih efisien dan cepat sehingga waktu dan cost yang dihabiskan untuk riset dapat diminimalisir.

## Analytic Approach : 
Dalam hal analytic approach ini, perlu adanya proses menganalisis data untuk menemukan pola dari fitur-fitur (kriteria) yang ada, yang membedakan satu mobil dengan mobil lainnya. Maka dari itu, kita akan membangun suatu model **regresi** yang akan membantu perusahaan untuk dapat menyediakan 'tool' prediksi harga mobil bekas yang baru masuk dalam daftar syarah.com dengan akurat, yang mana akan berguna untuk meningkatkan pendapatan perusahaan. 

## Metric Evaluation : 
Evaluasi metrik yang akan digunakan adalah RMSE, MAE, dan MAPE, di mana :

- RMSE adalah nilai rataan akar kuadrat dari error,
- MAE adalah rataan nilai absolut dari error,
- MAPE adalah rataan persentase error yang dihasilkan oleh model regresi.

Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, semakin akurat model dalam memprediksi harga mobil bekas dengan mempertimbangkan limitasi fitur yang digunakan. Dua metric utama, yaitu RMSE dan MAE, memiliki perbedaan signifikan. RMSE lebih sensitif terhadap kesalahan besar karena menggunakan kuadrat dari kesalahan, sedangkan MAE menggunakan nilai absolut kesalahan. Dalam konteks prediksi harga mobil bekas, kesalahan besar dapat memiliki dampak finansial yang besar, terutama jika model memprediksi harga yang jauh dari nilai sebenarnya. Oleh karena itu, untuk kasus ini, RMSE lebih relevan karena memberikan perhatian khusus terhadap kesalahan besar yang dapat menyebabkan kerugian yang signifikan bagi pengguna model, terutama jika digunakan untuk menentukan harga jual mobil bekas. Sehingga, RMSE memberikan gambaran yang lebih akurat tentang seberapa baik model memprediksi harga mobil bekas. 

## Data Undertanding : 
Dataset ini berisi 5624 data mobil bekas yang diambil dari syarah.com, Berikut beberapa features datanya : 

| Attribute    | Description                                | Data Type  |
|--------------|--------------------------------------------|------------|
| Type         | Type of used car.                          | object     |
| Region       | The region in which the used car was offered for sale. | object |
| Make         | The company name.                          | object     |
| Gear_Type    | Gear type size of used car.                | object     |
| Origin       | Origin of used car.                        | object     |
| Options      | Options of used car.                       | object     |
| Year         | Manufacturing year.                        | int64      |
| Engine_Size  | The engine size of used car.               | float64    |
| Mileage      | Mileage of used car.                       | int64      |
| Negotiable   | True if the price is 0, that means it is negotiable. | bool |
| Price        | Used car price.                            | int64      |

## Steps : 

### Data Preprocessing 
- Understanding and Handling Anomaly
- Understanding and Handling Outlier
- Melihat korelasi feature
  
## Modelling 
- Splitting
- Benchmarking
- Hyperparam Tuning
- Predict
- Evaluation Model : Performance Comparison & Feature Importances

## Conclusion 
- Best model yang dapat diimplementasikan di data ini adalah XGBoost Regresor degan hyperparameter tuning di : 
    1. colsample_bytree : 0.8
    2. gamma : 0.01 
    3. learning_rate : 0.1 
    4. max_depth : 7
    5. min_child_weight : 3 
    6. n_estimators : 100 
    7. subsample : 0.8 <br>

- Jika ditarik kesimpulan project ini dapat menggunakan model untuk memprediksi harga mobil bekas dengan limitasi harga yang berkisar antara 5.000 SAR hingga 182.000 SAR saja, lalu jumlah kilometer yang terletak diantara 100.000 Km hingga 900.000 Km (Limitasi).

- Jika dilihat dari feature yang penting, `Year`, `Engine_Size` & `Make` merupakan feature penting yang mempengaruhi terhadap target `Price`.

- Dapat disimpulkan bahwa bila nanti model yang ini digunakan untuk memperkirakan harga mobil pada rentang nilai seperti yang dilatih terhadap model (dengan limitasi `Price` berkisar antara 5.000 SAR hingga 182.000 SAR), maka perkiraan harga rata-rata akan meleset kurang lebih sebesar 15.778,43 SAR (RMSE) dan persentase rata-rata error nya sekitar 22,1% (MAPE) dari harga yang mungkin seharusnya dapat diprediksi. Bahkan dalam model ini pun tidak menuntup kemungkinan jika hasil prediksi bahkan meleset lebih jauh lagi karena masih terdapat bias yang dihasilkan masih cukup tinggi jika kita melihat harga aktual dan prediksinya. Bias yang terjadi ini dalam pemodelan ini karena minimnya feature yang merepresentasikan variasi spesifikasi mobil seperti, termasuk klasik atau tidak mobil ini, terdapat garansi atau tidak, pernah mengalami permasalahan pada mesin atau tidak dan masih masih banyak lagi.

- Tidak hanya itu, Limitasi pada model ini tentu memiliki pengaruh terhadap data testing baru yang nantinya akan digunakan sebagai model prediksi harga mobil. Karena dalam melakukan pemodelan data yang ada disini sudah dibersihkan sesuai dengan pertimbangan, maka hasil prediksi model dapat dikatakan tidak dipercaya. Namun ketika data telah disesuaikan dengan limitasi sebelumnya, maka hasil prediksi dapat dipercaya dengan kesalahan errornya.

- Pada tahap optimasi model, saya juga mencoba mencari model terbaik dari XGBoost dengan memberikan perbedaan proses scaling terhadap feature numeriknya (feature enginering), dan dapat disimpulkan masing-masing scaling tidak memberikan pengaruh terhadap hasil skor jika dilihat dari RMSE.

- Untuk melihat bagaimana model memprediksi data testing apakah underprice atau overprice dapat disimpulkan melalui residualnya. Data yang diprediksi **overprice** berjumlah **393** data, dan yang diprediksi **underprice** berjumlah **303**. Hal ini tentu akan menjawab Goals dari pembuatan model untuk memprediksi harga mobil bekas dimana untuk mencari keuntungan, harga yang cenderung overprice akan baik untuk dijual dan harga yang underprice cenderung baik untuk dibeli lalu dijual kembali dengan melakukan reparasi terlebih dahulu. 

## Rekomendasi 

- Terkait dengan limitasi untuk dalam pemodelan ini, sebaiknya jumlah data diperbanyak menjadi lebih dari dari 3000an (jumlah data yang sudah dibersihkan), agar model dapat memprediksi harga lebih akurat dari banyaknya variasi data juga. (Penambahan data ini perlu diutamakan terhadap data yang representasi variasinya tergolong sedikit). 

- Penambahan feature baru yang merepresentasikan variasi spesifikasi mobil seperti, apakah mobil ini merupakan jenis mobil klasik, terdapat garansi atau tidaknya, atau kondisi mobil terbaru, yang mempengarahui dalam menentukan harga mobil bekas. 

- Menggunakan Optuna sebagai Hyperparameter tuning optimization untuk improve performance dari model yang dipilih, atau penggunaan model lain untuk meminimalisir error yang dihasilkan.

- Penggunaan model yang lain dengan target baru untuk  mengklasifikasikan apakah mobil yang terjual ini menguntungkan bagi perusahaan atau tidak. Model klasifikasi ini berguna bagi perusahaan untuk memotong cost servis mobil dengan kondisi sangat buruk, atau sebagai bahan pertimbangan mobil tetap diiklankan atau tidak (Marketing Analyst).

- Dengan menunjukkan harga mana saja yang overprice dan underprice akan lebih baik juga bagi perusahaan untuk memberikan pertimbangan khusus harga mana yang dirasa overprice atau underprice yang masuk akal, dengan begitu perusahaan akan mencapai keuntungan dan bagi pelanggan menemukan harga yang sesuai dengan kriteria atau spesifikasi mobilnya. 



