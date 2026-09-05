# Gender Classification

Proyek klasifikasi gender suara menggunakan fitur **Mel-Frequency Cepstral Coefficients (MFCC)** dan algoritma **K-Nearest Neighbors (KNN)**. Notebook di repository ini mencakup pemuatan data, pemeriksaan audio, eksplorasi data, eksperimen parameter MFCC dan KNN, evaluasi model, serta pengujian menggunakan data eksternal.

## Alur Proyek

1. Membaca metadata dan audio dari dataset.
2. Memfilter kelas `male_masculine` dan `female_feminine`.
3. Mengekstraksi MFCC dari audio.
4. Membagi data menjadi data training dan testing.
5. Melakukan standardisasi fitur.
6. Melatih model KNN.
7. Mengukur accuracy, precision, recall, F1-score, dan confusion matrix.
8. Membandingkan beberapa kombinasi jumlah MFCC dan nilai K.
9. Menguji model menggunakan data eksternal.

## Struktur File

### Notebook eksplorasi dan praproses

| File | Keterangan |
|---|---|
| `ablasi.ipynb` | Eksperimen ablasi untuk melihat pengaruh komponen atau parameter fitur terhadap hasil klasifikasi. |
| `ablasidata.ipynb` | Analisis ablasi pada data dan perbandingan hasil pengujian. |
| `distribusi_durasi_audio.ipynb` | Menganalisis distribusi durasi file audio. |
| `distribusi_label.ipynb` | Menampilkan distribusi jumlah data untuk setiap label gender. |
| `eda_tsne.ipynb` | Exploratory Data Analysis dan visualisasi fitur menggunakan t-SNE. |
| `eksperimenunknown.ipynb` | Eksperimen prediksi atau analisis untuk data dengan label yang belum diketahui. |
| `heatmap_mfcc.ipynb` | Membuat heatmap untuk memvisualisasikan nilai atau pola fitur MFCC. |
| `spectogram.ipynb` | Membuat dan menganalisis spektrogram audio. |
| `waveform.ipynb` | Membuat dan menganalisis bentuk gelombang audio. |

### Notebook pengujian data eksternal

| File | Keterangan |
|---|---|
| `dataeksternal.ipynb` | Pipeline lengkap klasifikasi menggunakan data utama dan pengujian pada data eksternal. Notebook ini memuat ekstraksi MFCC, training KNN, prediksi, dan evaluasi data eksternal. |

### Notebook eksperimen MFCC dan KNN

Nama file mengikuti pola `mX-kY,jumlah_mfcc,nilai_k.ipynb`.

- `m1`: 13 MFCC
- `m2`: 18 MFCC
- `m3`: 20 MFCC
- `m4`: 24 MFCC
- `k1` sampai `k4`: variasi nilai K pada KNN

| Kelompok file | Isi |
|---|---|
| `m1-k1,13,3.ipynb` sampai `m1-k4,13,9.ipynb` | Eksperimen dengan 13 MFCC dan nilai K 3, 5, 7, serta 9. |
| `m2-k1,18,3.ipynb` sampai `m2-k4,18,9.ipynb` | Eksperimen dengan 18 MFCC dan nilai K 3, 5, 7, serta 9. |
| `m3-k1,20,3.ipynb` sampai `m3-k4,20,9.ipynb` | Eksperimen dengan 20 MFCC dan nilai K 3, 5, 7, serta 9. |
| `m4-k1,24,3.ipynb` sampai `m4-k4,24,9.ipynb` | Eksperimen dengan 24 MFCC dan nilai K 3, 5, 7, serta 9. |
| `m1-k1,13,3 fix.ipynb` | Versi perbaikan dari eksperimen 13 MFCC dengan K=3. |

### Rekapitulasi dan hasil

| File | Keterangan |
|---|---|
| `tabeleksperimen.ipynb` | Menggabungkan atau merangkum hasil seluruh eksperimen. |
| `grafik_tabel.ipynb` | Membuat grafik berdasarkan tabel hasil eksperimen. |
| `grafik_tabel.html` | Versi HTML dari visualisasi tabel atau grafik hasil eksperimen. |
| `hasil_eksperimen.xlsx` | File spreadsheet berisi rekapitulasi hasil eksperimen. |
| `grid_confusion_matrix_8_eksperimen.png` | Grid confusion matrix dari delapan kombinasi eksperimen. |
| `grafik_8_eksperimen_semua_metrik.png` | Perbandingan seluruh metrik dari delapan eksperimen. |
| `gender_distribution.png` | Grafik distribusi label gender. |
| `tsne_3d_all_genders.png` | Visualisasi t-SNE tiga dimensi untuk seluruh kelompok gender. |

### Gambar hasil analisis

| File | Keterangan |
|---|---|
| `output akurasi.png` | Grafik nilai accuracy. |
| `output f1-score.png` | Grafik nilai F1-score. |
| `output confusion matrix terbaik.png` | Confusion matrix dari eksperimen terbaik. |
| `output seluruh confusion matrix.png` | Kumpulan confusion matrix dari beberapa eksperimen. |
| `output data eksternal.png` | Hasil atau visualisasi pengujian data eksternal. |
| `output eda tsne.png` | Hasil visualisasi EDA dan t-SNE. |
| `output eda tsne fix.png` | Versi perbaikan visualisasi EDA dan t-SNE. |
| `output heatmap.png` | Hasil visualisasi heatmap MFCC. |
| `output SPECTOGRAM.png` | Contoh atau hasil visualisasi spektrogram. |
| `output waveform.png` | Contoh atau hasil visualisasi waveform. |
| `output unknown.png` | Hasil eksperimen untuk data unknown. |

### Dataset dan konfigurasi

| Item | Keterangan |
|---|---|
| `validated.tsv` | Metadata dataset utama. File ini di-ignore dan tidak dipublish ke GitHub. |
| `clips/` | Folder audio dataset utama. Folder ini di-ignore dan tidak dipublish ke GitHub. |
| `Dataeksternal/` | Folder audio eksternal yang dikelompokkan berdasarkan label. Folder ini di-ignore dan tidak dipublish ke GitHub. |
| `.gitignore` | Mengatur file dataset dan environment lokal agar tidak masuk repository. |
| `.venv/`, `.venv-1/` | Environment Python lokal. Keduanya di-ignore dan tidak dipublish ke GitHub. |

## Teknologi yang Digunakan

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Librosa
- Scikit-learn
- Matplotlib
- SoundFile
- tqdm

## Cara Menjalankan

1. Clone repository ini.
2. Siapkan dataset lokal sesuai struktur berikut:

   ```text
   validated.tsv
   clips/
   Dataeksternal/
   ├── female_feminine/
   └── male_masculine/
   ```

3. Buat atau aktifkan environment Python.
4. Install dependensi yang digunakan notebook:

   ```bash
   pip install numpy pandas librosa scikit-learn matplotlib soundfile tqdm openpyxl jupyter
   ```

5. Buka notebook melalui Jupyter Notebook atau VS Code.
6. Jalankan notebook praproses terlebih dahulu, kemudian notebook eksperimen dan rekapitulasi hasil.

## Catatan Dataset

Dataset audio dan metadata sengaja tidak dimasukkan ke repository karena ukuran dan sifatnya sebagai data lokal. Notebook tetap tersimpan, tetapi notebook yang membutuhkan dataset hanya dapat dijalankan setelah file dataset tersedia di lokasi yang sesuai.