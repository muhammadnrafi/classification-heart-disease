# Heart Disease Prediction Using Machine Learning

Notebook ini berisikan `end-to-end` machine learning untuk mengklasifikasikan apakah seseorang memiliki permasalahan pada penyakit jantung atau tidak.

Berikut adalah beberapa tahapan / framework dari notebook secara keseluruhan:

* **Exploratory data analysis (EDA)** - Proses untuk menggali isi dari sebuah dataset.
* **Model training** - Membuat sebuah model untuk belajar dari dataset dan menghasilkan prediksi target berdasarkan variabel/fitur di dataset.
* **Model evaluation** - Melakukan evaluasi terhadap setiap model dalam membuat prediksi. 
* **Model comparison** - Melakukan perbandinan terhadap setiap model yang telah untuk mendapatkan model mana yang akan digunakan.
* **Model fine-tuning** - Mencoba dan melakukan peningkatan performa pada model, sejauh mana model dapat menghasilkan nilai prediksi.
* **Feature importance** - Menentukan fitur mana yang memiliki pengaruh signifikan terhadap output / prediksi.
* **Reporting what we've found** - Membuat laporan terhadap aksi yang telah dilakukan.

## 1. Pernyataan Permasalahan
Pada kasus ini, permasalahan yang akan dibahas adalah mengenai **binary classification**. Permasalahan ini akan hanya menghasilkan dua buah output yaitu ya / tidak, 1 / 0 dst. Hal ini karena kita akan membahas mengenai permasalahan dengan menggunakan berbagai fitur dalam menentukan apakah seseorang memiliki permasalahan jantung atau tidak.

> Berdasarkan data yang diberikan oleh pasien, apakah dapat memprediksi seorang pasien memiliki permaslahan jantung?

## 2. Data

Data ini berasal dari [Kaggle](https://www.kaggle.com/datasets/sumaiyatasmeem/heart-disease-classification-dataset). Pada original database-nya ([Cleveland database](https://archive.ics.uci.edu/ml/datasets/heart+Disease) from UCI Machine Learning Repository.) dataset ini berisikan 76 attributes, namun pada projek ini hanya akan menggunakan 14 attributes saja sesuai dengan dataset yang berasal dari [Kaggle].

Attributes atau fitur dapat di identifikasikan sebagai **independent variables** sedangkan fitur target dapat di identifikasikan sebagai **dependent variables**.


## 3. Evaluation

Projek ini merupakan sebuah projek yang berlatar belakang dari permasalahan klasifikasi, sehingga dalam projek ini kita akan menggunakan `accuracy` sebagai metric pengukuran keberhasilan projek ini.

> Goal : Menghasilkan machine learning dengan tingkat ke akuratan sebesar 80% dalam memprediksi apakah seseorang memiliki permasalahan pada jantung.


## 4. Features

Berikut adalah beberapa fitur dan target yang akan digunakan pada project ini.
1. age - age in years 
2. sex - (1 = male; 0 = female) 
3. cp - chest pain type 
    * 0: Typical angina: chest pain related decrease blood supply to the heart
    * 1: Atypical angina: chest pain not related to heart
    * 2: Non-anginal pain: typically esophageal spasms (non heart related)
    * 3: Asymptomatic: chest pain not showing signs of disease
4. trestbps - resting blood pressure (in mm Hg on admission to the hospital)
    * anything above 130-140 is typically cause for concern
5. chol - serum cholestoral in mg/dl 
    * serum = LDL + HDL + .2 * triglycerides
    * above 200 is cause for concern
6. fbs - (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false) 
    * '>126' mg/dL signals diabetes
7. restecg - resting electrocardiographic results
    * 0: Nothing to note
    * 1: ST-T Wave abnormality
        - can range from mild symptoms to severe problems
        - signals non-normal heart beat
    * 2: Possible or definite left ventricular hypertrophy
        - Enlarged heart's main pumping chamber
8. thalach - maximum heart rate achieved 
9. exang - exercise induced angina (1 = yes; 0 = no) 
10. oldpeak - ST depression induced by exercise relative to rest 
    * looks at stress of heart during excercise
    * unhealthy heart will stress more
11. slope - the slope of the peak exercise ST segment
    * 0: Upsloping: better heart rate with excercise (uncommon)
    * 1: Flatsloping: minimal change (typical healthy heart)
    * 2: Downslopins: signs of unhealthy heart
12. ca - number of major vessels (0-3) colored by flourosopy 
    * colored vessel means the doctor can see the blood passing through
    * the more blood movement the better (no clots)
13. thal - thalium stress result
    * 1,3: normal
    * 6: fixed defect: used to be defect but ok now
    * 7: reversable defect: no proper blood movement when excercising 
14. target - have disease or not (1=yes, 0=no) (= the predicted attribute)


## Kesimpulan
1. Dari hasil eksperimen diatas, dapat disimpulkan dengan menggunakan algoritma Logistic Regression menghasilkan tingkat akurasi maksimal sebesar 84% yang dimana nilai tersebut dapat dikategorikan cukup baik. Namun untuk menghasilkan tingkat akurasi yang lebih baik lagi, dapat mencoba menggunakan algoritma lainnya seperti CatBoost atau XGBoost.

2. Dari total 13 fitur, kita mendapatkan top 5 fitur yang memiliki pengaruh yang signifikan terhadap output yang dihasilkan. berikut adalah urutannya: Sex, Thal, Cp, Ca dan Exang

3. Algoritma machine learning yang telah dibuat sudah cukup mampu menentukan klasifikasi dari pasien apakah memiliki permasalahan jantung atau tidak. Dengan mendeteksi potensi permasalahan tersebut, kita dapat mencegah terjadi nya hal potensi tersebut untuk terjadi.
