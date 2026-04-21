# Perbandingan Metode Canny Edge Detection dan YOLO untuk Deteksi Sampah Laut pada Citra Bawah Air

## Deskripsi
Proyek ini membandingkan dua pendekatan dalam mendeteksi sampah laut (marine debris) pada citra bawah air, yaitu metode klasik **Canny Edge Detection** dan metode berbasis deep learning **YOLO (You Only Look Once)**.

Citra bawah air memiliki karakteristik yang menantang, seperti pencahayaan rendah, kekeruhan, dan distorsi warna. Kondisi ini memengaruhi proses deteksi objek, sehingga diperlukan metode yang mampu bekerja pada kondisi visual yang tidak ideal.

---

## Tujuan
- Menganalisis performa metode edge detection pada citra bawah air  
- Mengevaluasi kinerja model YOLO dalam mendeteksi sampah laut  
- Membandingkan efektivitas kedua metode berdasarkan hasil deteksi  

---

## Dataset
Dataset yang digunakan adalah SeaClear Marine Debris Dataset:  
https://www.kaggle.com/datasets/jocelyndumlao/seaclear-marine-debris-detection-and-segmentation  

Dataset ini berisi citra bawah laut dengan anotasi bounding box dalam format **COCO (JSON)** yang digunakan sebagai ground truth dalam evaluasi.

---

## Metodologi

### 1. Preprocessing
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
- IoU (Intersection over Union)  
- Precision  
- Recall  
- mAP (mean Average Precision)  

---

## Hasil

| Metode | IoU | mAP50 | Precision | Recall |
|--------|-----|------|----------|--------|
| Edge Detection | 1.25% | - | ~0% | ~0% |
| YOLO | - | 31.4% | 54% | 48% |

### Ringkasan
- Edge detection menghasilkan banyak tepi, namun sebagian besar bukan objek sampah (noise)  
- YOLO mampu mendeteksi objek dengan bounding box yang lebih akurat  
- YOLO memiliki performa yang jauh lebih baik dibandingkan edge detection pada citra bawah air  

---

## Teknologi yang Digunakan
- Python  
- OpenCV  
- YOLO (Ultralytics / Darknet)  
- NumPy  
- Matplotlib  

---

## Kesimpulan
Metode **YOLO** lebih efektif dalam mendeteksi sampah laut dibandingkan **Canny Edge Detection**, terutama pada kondisi citra bawah air yang kompleks. Pendekatan deep learning mampu memahami fitur objek dengan lebih baik, sehingga menghasilkan deteksi yang lebih akurat dan konsisten.
