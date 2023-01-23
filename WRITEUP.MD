# No. 2: Estimasi Luas Kolam, Jumlah Kolam, dan Geo-things
Skill Task - ML Engineer RnD. Ini adalah cara saya dalam mengetahui luas setiap kolam dalam 5 site berbeda.

## Playing with Assumptions and Constraints
Metrics adalah hal penting, termasuk dalam task estimasi luas kolam. Selisih luas aktual dan luas hasil prediksi adalah salah satu bentuk metric. Untuk mendapatkan selisih yang minimal, bisa jadi proses yang panjang dan lebih tidak worth it daripada estimasi kasar dan mengerjakan task lainnya.

Asumsi tanggal di peta adalah Google Earth adalah sama seperti kondisi sekarang (jika Gibran beneran datang ke lokasi secara fisik).

## Metodologi saya
Mengingat site yang hendak ditinjau hanya ada 5 dan waktu pengerjaan hanya sehari, maka lebih mudah menurut saya untuk meninjau menggunakan estimasi manual tenaga manusia. Jika menggunakan semacam "pools segmentation" untuk waktu sependek itu dan jumlah objek minimal, risk-rewardnya tidak mencukupi.

## Cara Menghitung Jumlah Kolam
1. Hitung satu per satu sebagaimana menghitung domba di pigora ketika hendak tidur

## Cara Mengestimasi Luas Kolam
1. Buka Google Earth, masukkan lokasi 
![Masukkan koordinat ke Google Earth](https://images2.imgbox.com/84/86/ACOby6cx_o.png)
2. Cari kolam yang ukurannya terlihat paling tengah (perkiraan rata2 luas) dengan kolam sekitarnya > Klik measure distance > buat titik pertama > lalu kitari 1 kotak kolam
![enter image description here](https://images2.imgbox.com/c4/23/9OYTZBcb_o.jpg)
3. Untuk mengukur banyak kolam sekaligus, kitari saja hingga jadi closed loop ke banyak kolam
![enter image description here](https://images2.imgbox.com/29/11/GrX3SwAR_o.jpg)
*img 3a*
![enter image description here](https://images2.imgbox.com/12/c3/szJTTkpo_o.jpg)
*img 3b*

4. Luas yang diukur lebih dari kolam tadi dikurangin dengan area border/tanggul. Perhatikan pengurangan area tanggul
![enter image description here](https://images2.imgbox.com/90/78/2G0wmndU_o.jpg)
*img 4a*
Kemudian, subarea tanggul tadi, dikalikan dengan jumlah tanggul yang ada di dalam scope luasan yang diukur di nomor 2.
Catatan: Untuk mempermudah perhitungan, pastikan kolam yang diukur tadi dimensi "bordernya" (tanggul) cenderung homogen. Perhatikan imagery berikut:
![enter image description here](https://images2.imgbox.com/00/fa/jDTDfu3b_o.jpg)
*img 4b*
Bisa dilihat di img 4b tanggul yg bawah jauh lebih tebal daripada yang atas, menyebabkan perhitungan berikutnya menjadi lebih rumit karena harus ukur tanggul minimal 2x.
Begitu juga pada img 3a, terlihat ada area berwarna merah tidak diikutkan dalam loop area pengukuran karena tidak homogen tanggulnya dari loop (area ROI) ke kolam di area warna merah.