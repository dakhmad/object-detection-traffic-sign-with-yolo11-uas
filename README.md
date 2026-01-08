# Tim-Deep-Learning
Ini Uas Deep Learning

# Deteksi Objek Rambu Lalu Lintas Menggunakan YOLO11

1. Identitas Kelompok 
   Dani Akhmad Maulana (2230511007) <br>
   Raihan Aulia Rahman (2230511037) <br>
   Faisal Triaputra (2230511042) <br>
   Raditya Bagja Saputra (2230511045) <br>
   Rifqi Fakhrezi Pasya (2530517003) <br>

2. Latar Belakang dan Tujuan
   1) Latar Belakang
   Rambu lalu lintas memegang peranan vital dalam menjaga ketertiban dan
keselamatan pengguna jalan raya. Informasi visual yang disampaikan oleh rambu
berfungsi mengatur arus lalu lintas dan memberikan peringatan dini terhadap
potensi bahaya. Namun, efektivitas rambu ini sangat bergantung pada kemampuan
pengemudi untuk melihat dan memahaminya dalam waktu singkat. Data
kecelakaan lalu lintas menunjukkan bahwa kelalaian pengemudi dalam
memperhatikan rambu sering menjadi penyebab utama insiden di jalan raya. Faktor
fisik seperti kelelahan, gangguan konsentrasi, atau kondisi lingkungan seperti hujan
lebat dan pencahayaan minim sering kali menurunkan kemampuan visual
pengemudi secara drastis.
Perkembangan teknologi kecerdasan buatan, khususnya dalam bidang visi
komputer (computer vision), menawarkan solusi teknis untuk mengatasi
keterbatasan persepsi manusia tersebut. Penerapan teknologi ini memungkinkan
komputer untuk memproses dan memahami informasi visual dari jalan raya secara
otomatis layaknya pengamatan manusia. Kebutuhan krusial dalam implementasi ini
adalah ketersediaan algoritma deteksi objek yang mampu beroperasi dengan
performa tinggi untuk memberikan hasil analisis secara waktu nyata (real-time).
Tantangan utama dalam pengembangan teknologi ini terletak pada pemilihan
arsitektur model yang mampu menyeimbangkan kecepatan pemrosesan data
dengan tingkat ketepatan deteksi yang tinggi, terutama saat menghadapi objek
berukuran kecil atau kondisi visual lingkungan yang kompleks dan dinamis.
Penelitian ini memilih algoritma YOLOv11 (You Only Look Once versi 11)
sebagai metode utama deteksi rambu lalu lintas. Sebagai iterasi terbaru dari
keluarga YOLO, model ini membawa pembaruan arsitektur yang signifikan untuk
meningkatkan efisiensi komputasi tanpa mengorbankan akurasi. Penggunaan
YOLOv11 dalam penelitian ini didasari oleh kemampuannya memproses citra
dengan latensi rendah, yang merupakan syarat mutlak bagi aplikasi keselamatan
berkendara. Penelitian ini akan berfokus pada penerapan dan pengujian kinerja
YOLOv11 dalam mendeteksi berbagai kelas rambu lalu lintas pada dataset yang
merepresentasikan kondisi jalan sesungguhnya.

  2) Tujuan
  Berdasarkan latar belakang dapat diidentifikasi masalah yang ada adalah
sebagai berikut:
1. Menerapkan algoritma YOLOv11 untuk mendeteksi dan mengklasifikasikan
jenis rambu lalu lintas secara otomatis.
2. Mengukur tingkat akurasi model dalam mengenali objek pada berbagai kondisi
pencahayaan dan lingkungan.
3. Mengevaluasi kecepatan inferensi model untuk memastikan kelayakan sistem
dalam penggunaan waktu nyata (real-time)

3. Deskripsi Dataset
   Dataset ini terdiri dari 2.100 citra digital yang terbagi rata ke dalam 21
   kelas kategori (masing-masing 100 citra) untuk mencegah bias model.
   Seluruh citra telah distandarisasi ke resolusi 640x640 piksel.
Kategori rambu yang mencakup
  1) Lalu Lintas: Lampu merah, kuning, dan hijau.
  2) Larangan: Belok (kanan/kiri), berhenti, parkir, memutar balik, masuk,
     dan larangan berjalan terus.
  3) Peringatan: APILL, zebra cross, perlintasan kereta api, simpang tiga,
     dan rambu tambahan.
  4) Perintah & Petunjuk: Jalur masuk, area parkir, halte bus,
     lokasi putar balik, dan penyeberangan jalan.

4. Metodologi dan Arsitektur Model
   1) Metodologi
   Penelitian ini menggunakan metode CRISP-DM (Cross Industry Standard
Process for Data Mining) sebagai kerangka kerja dalam pengembangan sistem
deteksi rambu lalu lintas berbasis deep learning. CRISP-DM dipilih karena
menyediakan tahapan yang sistematis, terstruktur, dan bersifat iteratif, sehingga
mampu mengarahkan proses penelitian mulai dari pemahaman permasalahan
hingga evaluasi dan kesiapan penerapan model. Dalam konteks deep learning,
CRISP-DM memungkinkan integrasi antara kebutuhan permasalahan nyata dengan
proses pengolahan data, pemodelan, serta evaluasi kinerja model secara ilmiah dan
terukur.
  2) Arsitektur Model
  Arsitektur model yang digunakan dalam penelitian ini adalah YOLO11 (You
Only Look Once versi 11), yang merupakan salah satu algoritma object detection
berbasis deep learning dengan pendekatan single-stage detector. YOLO11
dirancang untuk melakukan deteksi objek secara cepat dan akurat dengan
memproses citra masukan hanya dalam satu kali inferensi. Pendekatan ini
memungkinkan sistem untuk secara simultan memprediksi lokasi objek berupa
bounding box, tingkat kepercayaan (confidence score), serta kelas objek yang
terdeteksi, sehingga sangat sesuai untuk kebutuhan deteksi rambu lalu lintas secara
real-time.

5. Hasil dan Evaluasi
   Berdasarkan hasil evaluasi menggunakan model YOLOv11s, diperoleh:
1.	Nilai mAP@0.5 sebesar 0.9703 dan mAP@0.5:0.95 sebesar 0.7655, yang menunjukkan bahwa
    model memiliki tingkat akurasi deteksi yang sangat tinggi baik pada ambang
  	IoU moderat maupun ketat.
2.  Nilai precision sebesar 0.9356 mengindikasikan bahwa sebagian besar prediksi
    yang dihasilkan model adalah benar,
3.  Sementara recall sebesar 0.9628 menunjukkan kemampuan model yang sangat baik dalam
    mendeteksi hampir seluruh rambu lalu lintas yang terdapat pada citra uji.
Penerapan early stopping dengan patience 20 menyebabkan proses pelatihan dihentikan secara otomatis pada epoch ke-50
menandakan bahwa model telah mencapai kondisi konvergen sebelum mencapai batas maksimum 80 epoch.
Secara keseluruhan, hasil ini membuktikan bahwa penggunaan early stopping mampu meningkatkan efisiensi pelatihan
tanpa menurunkan performa model, serta menghasilkan model terbaik (best.pt) yang andal untuk deteksi rambu lalu lintas secara akurat dan konsisten.

6. Analisis dan Pembahasan
   - Kinerja Model: Model YOLO11s terbukti sangat efektif untuk kasus ini. Nilai mAP50 yang mencapai angka di atas 95% dalam 30 epoch pertama menandakan bahwa model dapat mempelajari
     fitur-fitur rambu lalu lintas (bentuk, warna, simbol) dengan sangat cepat dan akurat
   - Stabilitas : Grafik _loss_ (box_loss, cls_loss, dfl_loss) menunjukkan tren penurunan yang konsisten, mengindikasikan tidak adanya _overfitting_ yang signifikan pada tahap ini.
   - Efisiensi : Penggunaan model versi "small" (yolo11s) memberikan keseimbangan yang baik antara jumlah parameter (ringan) dan akurasi, mendukung tujuan implementasi _real time_.
  
7. Kesimpulan
   Proyek ini berhasil mengembangkan model deteksi objek untuk 21 jenis rambu lalu lintas menggunakan YOLO11.
   Dengan memanfaatkan dataset yang di augmentasi menjadi 5.380 gambar, model mencapai performa impresif dengan
   mAP50 sekitar 97%. hal ini membuktikan bahwa pendektan Computer Vision menggunakan YOLO11 layak dan efektif
   untuk diterapkan sebagai sistem bantuan pengemudi guna meningkatkan keselamatan di jalan raya

8. Referensi
   Algoritma : YOLO11
   Platform Dataset & Anotasi : Roboflow
   Sumber Data Awal : kaggle
   Library Pendukung : Pytorch, matplotlib, Pillow, OpenCV


