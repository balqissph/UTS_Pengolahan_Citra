# Perbandingan Metode Canny Edge Detection dan YOLO untuk Deteksi Sampah Laut pada Citra Bawah Air

## Deskripsi
<<<<<<< HEAD
Proyek ini membandingkan dua pendekatan dalam mendeteksi sampah laut (marine debris) pada citra bawah air, yaitu metode klasik **Canny Edge Detection** dan metode berbasis deep learning **YOLO (You Only Look Once)**.

Citra bawah air memiliki karakteristik yang menantang, seperti pencahayaan rendah, kekeruhan, dan distorsi warna. Kondisi ini memengaruhi proses deteksi objek, sehingga diperlukan metode yang mampu bekerja pada kondisi visual yang tidak ideal.
=======
Penelitian ini membahas deteksi sampah laut (*marine debris*) pada citra bawah air menggunakan pendekatan pengolahan citra digital dan deep learning. Fokus utama penelitian adalah membandingkan performa metode klasik **Canny Edge Detection** dengan metode berbasis deep learning **YOLO (You Only Look Once)**.

Permasalahan utama berasal dari kondisi citra bawah air yang memiliki pencahayaan rendah, kekeruhan tinggi, serta distorsi warna, sehingga menyulitkan proses deteksi objek.
>>>>>>> 58a075991abdec553889b395a663ec6f2802cfbe

---

## Tujuan
<<<<<<< HEAD
- Menganalisis performa metode edge detection pada citra bawah air  
- Mengevaluasi kinerja model YOLO dalam mendeteksi sampah laut  
- Membandingkan efektivitas kedua metode berdasarkan hasil deteksi  
=======
- Menganalisis pengaruh kondisi citra bawah air terhadap deteksi objek  
- Menguji performa metode **Canny Edge Detection**  
- Menguji performa model **YOLO**  
- Membandingkan efektivitas kedua metode dalam mendeteksi sampah laut  
>>>>>>> 58a075991abdec553889b395a663ec6f2802cfbe

---

## Dataset
<<<<<<< HEAD
Dataset yang digunakan adalah SeaClear Marine Debris Dataset:  
https://www.kaggle.com/datasets/jocelyndumlao/seaclear-marine-debris-detection-and-segmentation  

Dataset ini berisi citra bawah laut dengan anotasi bounding box dalam format **COCO (JSON)** yang digunakan sebagai ground truth dalam evaluasi.
=======
Dataset yang digunakan adalah **SeaClear Marine Debris Dataset** ( https://www.kaggle.com/datasets/jocelyndumlao/seaclear-marine-debris-detection-and-segmentation ), yang berisi citra bawah laut dengan anotasi bounding box (format COCO).

Dataset ini digunakan untuk:
- Pengujian metode edge detection  
- Training dan evaluasi model YOLO  
>>>>>>> 58a075991abdec553889b395a663ec6f2802cfbe

---

## Metodologi

### 1. Preprocessing
<<<<<<< HEAD
Tahap preprocessing dilakukan berbeda untuk masing-masing metode:
- **Edge Detection**: citra dikonversi ke grayscale karena hanya memanfaatkan intensitas piksel  
- **YOLO**: preprocessing dilakukan otomatis oleh framework (normalisasi dan penyesuaian ukuran input)  

### 2. Split Data
Dataset dibagi menjadi:
- Training  
- Validation  
- Testing  

(Tahap ini digunakan untuk pelatihan model YOLO)

### 3. Deteksi Objek

#### Canny Edge Detection
- Deteksi tepi berdasarkan perubahan intensitas piksel  
- Ekstraksi kontur untuk menghasilkan bounding box  
- Tidak mengenali jenis objek (hanya struktur tepi)

#### YOLO
- Model deep learning untuk deteksi objek  
- Menghasilkan bounding box dan confidence score  
- Mampu mengenali lokasi dan jenis objek  

### 4. Evaluasi
Performa kedua metode dibandingkan menggunakan metrik:
=======
- Noise reduction  
- Peningkatan kontras  

### 2. Split Data (YOLO)
- Training  
- Validation  
- Testing  

### 3. Deteksi Objek
- **Canny Edge Detection** → ekstraksi tepi + bounding box dari kontur  
- **YOLO** → deteksi objek berbasis bounding box  

### 4. Evaluasi
>>>>>>> 58a075991abdec553889b395a663ec6f2802cfbe
- IoU (Intersection over Union)  
- Precision  
- Recall  
- mAP (mean Average Precision)  

---

<<<<<<< HEAD
## Hasil

| Metode | IoU | mAP50 | Precision | Recall |
|--------|-----|------|----------|--------|
| Edge Detection | 1.25% | - | ~0% | ~0% |
| YOLO | - | 31.4% | 54% | 48% |

### Ringkasan
- Edge detection menghasilkan banyak tepi, namun sebagian besar bukan objek sampah (noise)  
- YOLO mampu mendeteksi objek dengan bounding box yang lebih akurat  
- YOLO memiliki performa yang jauh lebih baik dibandingkan edge detection pada citra bawah air  
=======
## Metode yang Digunakan

### 🔹 Canny Edge Detection
Metode klasik untuk mendeteksi tepi berdasarkan perubahan intensitas piksel. Tidak mengenali objek secara spesifik, hanya struktur tepi.

### 🔹 YOLO (You Only Look Once)
Metode deep learning untuk deteksi objek secara langsung dalam satu proses, mampu mengenali lokasi dan jenis objek.
>>>>>>> 58a075991abdec553889b395a663ec6f2802cfbe

---

## Hasil

| Metode          | IoU     | mAP50  | Precision | Recall |
|----------------|--------|--------|----------|--------|
| Edge Detection | 1.25%  | -      | ~0%      | ~0%    |
| YOLO           | -      | 31.4%  | 54%      | 48%    |

### 🔍 Analisis
- **Edge Detection**
  - Banyak mendeteksi noise  
  - Tidak mampu membedakan objek sampah dengan background  

- **YOLO**
  - Deteksi lebih akurat  
  - Bounding box mendekati ground truth  
  - Lebih stabil pada kondisi citra kompleks  

---

## Kesimpulan
Metode **YOLO** menunjukkan performa yang jauh lebih baik dibandingkan **Canny Edge Detection** dalam mendeteksi sampah laut pada citra bawah air.

Pendekatan berbasis deep learning lebih efektif karena mampu memahami fitur kompleks, sedangkan metode edge detection hanya bergantung pada perubahan intensitas piksel.

---

## Pengembangan Selanjutnya
- Menggunakan metode **image enhancement** untuk memperbaiki kualitas citra  
- Menggunakan versi YOLO terbaru  
- Mengembangkan sistem deteksi secara **real-time**  

---

## Tools & Teknologi
- Python  
- OpenCV  
- YOLO (Ultralytics / Darknet)  
- SeaClear Dataset  

---

<<<<<<< HEAD
## Kesimpulan
Metode **YOLO** lebih efektif dalam mendeteksi sampah laut dibandingkan **Canny Edge Detection**, terutama pada kondisi citra bawah air yang kompleks. Pendekatan deep learning mampu memahami fitur objek dengan lebih baik, sehingga menghasilkan deteksi yang lebih akurat dan konsisten.
=======
## Catatan
Project ini dibuat sebagai bagian dari pembelajaran dan penelitian pada bidang **Pengolahan Citra Digital**.
>>>>>>> 58a075991abdec553889b395a663ec6f2802cfbe
