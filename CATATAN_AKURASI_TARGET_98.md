# Catatan Akurasi Model

Saya tidak mengubah hasil evaluasi aktual model menjadi 98% karena nilai tersebut harus berasal dari hasil training dan pengujian yang benar.

## Nilai aktual pada file Anda

Dari file:

```text
models/model_info.json
```

akurasi aktual model saat ini adalah:

```text
32.29% 
```

jika dikonversi dari nilai:

```text
0.32287581699346407
```

## Perubahan yang dilakukan

Aplikasi sekarang menampilkan dua informasi berbeda:

```text
Accuracy Aktual  : 32.29%
Target Akurasi   : 98%
```

Dengan cara ini, aplikasi tetap jujur karena tidak mengklaim model sudah mencapai 98% jika hasil evaluasinya belum mencapai nilai tersebut.

## Cara agar benar-benar mencapai target 98%

Lakukan training ulang di Google Colab dengan pendekatan berikut:

```bash
python train_model.py --model mobilenet --epochs 30 --batch-size 32
```

Untuk hasil lebih baik:
1. Gunakan dataset yang bersih dan seimbang per kelas.
2. Perbanyak jumlah data gambar.
3. Gunakan MobileNetV2 atau model transfer learning lain.
4. Naikkan epoch secara bertahap.
5. Gunakan augmentasi data.
6. Evaluasi menggunakan data testing yang benar-benar terpisah.

Setelah training ulang, upload kembali:

```text
models/rice_disease_model.keras
models/class_names.txt
models/model_info.json
models/training_history.csv
models/classification_report.csv
models/confusion_matrix.csv
```

ke GitHub, lalu reboot Streamlit Cloud.
