**Context**  
Sebuah perusahaan yang bergerak di bidang telekomunikasi memiliki data yang mewakili profil pelanggan yang telah meninggalkan perusahaan telekomunikasi. Peralihan layanan telekomunikasi dan layanan berbasis langganan lainnya berarti situasi ketika pelanggan meninggalkan penyedia layanan.

Target :

Yes : Meninggalkan penyedia langganan

No : Tidak meninggalkan penyedia langganan

**Problem Statement :**

Jika customer meninggalkan penyedia langganan, perusahaan telekomunikasi akan kehilangan pemasukannya dan perlu biaya, waktu, dan usaha untuk menggantikan pelanggan yang meninggalkan penyedia pelanggan. 

**Goals :**

Maka berdasarkan permasalahan tersebut, perusahaan telekomunikasi ingin memprediksi kemungkinan seorang customer yang akan meninggalkan penyedia langganan perusahaan tersebut atau tidak.

Dan juga, perusahaan ingin mengetahui faktor apa yang membuat seorang customer akan meninggalkan penyedia langganan perusahaan tersebut atau tidak.

**Analytic Approach :**

Jadi yang akan kita lakukan adalah menganalisis data untuk menemukan pola yang membedakan customer akan meninggalkan penyedia langganan perusahaan tersebut atau tidak.

Kemudian kita akan membangun model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas seorang customer akan meninggalkan penyedia langganan perusahaan tersebut atau tidak.

**Metric Evaluation**

Type 1 error : False Positive  
Konsekuensi: sia-sianya biaya, waktu dan usaha

Type 2 error : False Negative  
Konsekuensi: kehilangan pemasukkan jadi tidak terduga dan lebih besar daripada yang sudah pasti meninggalkan penyedia langganan

Berdasarkan konsekuensinya, maka sebisa mungkin yang akan kita lakukan adalah membuat model yang dapat mencegah kehilangan pemasukkan perusahaan tersebut dan meminimalisir pengeluaran untuk mencari pelanggan baru. Jadi nanti metric utama yang akan kita gunakan adalah Precision-Recall Score.

Model terbaik menggunakan Random Forest yang telah dituning dengan oversampling SMOTE dan threshold menggunalan PR Curve

Feature yang paling menyebabkan customer churn adalah biaya layanan bulanan (Monthly Charges) yang besar, Tenure yang pendek, dan kontrak bulanan

Dengan model ini, yang diprediksi customer tidak churn tetapi kenyataan sebaliknya berkurang banyak dan customer yang diprediksi churn sebaliknya

- Before tuning:
    - recall    :  40.31%
    - precision :  56.22%

- After threshold:
    - recall    :  97.67%
    - precision :  32.18%
