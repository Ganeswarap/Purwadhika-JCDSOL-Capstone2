# Purwadhika-JCDSOL-Capstone2
## Latar Belakang
  Sebuah perusahaan fiktif SAAS (Software as a Service) menyediakan perangkat lunak pemasaran dan penjualan. Perusahaan ini menjual produknya, yang berupa lisensi perangkat lunak, kepada perusahaan-perusahaan lain. Harga produk pada tiap transaksi bisa berbeda, sehingga pembelian produk yang sama dengan jumlah yang sama bisa memiliki total harga yang berbeda. Hal ini menyebabkan keuntungan dari masing-masing transaksi tidak hanya dipengaruhi oleh jenis produk dan jumlahnya. Hal ini juga memungkinan terjadinya transaksi dengan keuntungan negatif, yang merupakan kerugian bagi perusahaan.
### Pernyataan Masalah
  Perusahaan ingin mengetahui transaksi seperti apa yang memberikan keuntungan besar. Informasi ini dapat membantu perusahaan untuk menentukan keputusan yang bisa meningkatkan pendapatan perusahaan, seperti strategi pemasaran, kriteria perusahaan untuk diajak bermitra, dan besar diskon yang diberikan saat bertransaksi.
  Sebagai data analyst perusahaan fiktif ini, kita akan menocba menjawab pertanyaan berikut: Apa kriteria transaksi yang memberikan keuntungan yang besar, khususnya yang lebih dari rata-rata keuntungan.
## Data
  Dataset ini berisi 9994 baris yang berupa informasi dari penjualan perusahaan fiktif ini. Masing-masing baris merepresentasikan satu jenis produk dari satu pemesanan. Masing-masing jenis produk yang berbeda dari pemesanan yang sama akan dicatat sebagai transaksi yang berbeda. 19 kolom dataset ini terdiri dari:
1.  `Row ID`: ID untuk tiap Transaksi.
2.  `Order ID`: ID untuk tiap pemesanan.
3.  `Order Date`: Tanggal pemesanan.
4.  `Date Key`: Representasi numerik dari tanggal pemesanan.
5.  `Contact Name`: Nama pemesan.
6.  `Country`: Negara asal pemesanan.
7.  `City`: Kota asal pemesanan.
8.  `Region`: Region asal pemesanan.
9.  `Subregion`: Subregion asal pemesanan.
10. `Customer`: Nama perusahaan pemesan.
11. `Customer ID`: ID perusahaan pemesan.
12. `Industry`: Industri perusahaan pemesan.
13. `Segment`: Segmen industri perusahaan pemesan.
14. `Product`: Produk yang dipesan.
15. `License`: *Key* lisensi produk yang dipesan.
16. `Sales`: besar penjualan untuk transaksi ini.
17. `Quantity`: Jumlah produk yang dipesan di transaksi ini.
18. `Discount`: Diskon yang diberikan untuk transaksi ini.
19. `Profit`: Keuntungaan dari transaksi ini.
### Data Cleaning
Proses data cleaning yang dilakukan adalah
*   Mengubah tipe data kolom `Order Date`.
*   Membatasi nilai di kolom `Sales` dengan batas atas 2099.593 untuk mengatasi *outlier*.
*   Membatasi nilai di kolom `Profit` dengan batas atas 731.437 untuk mengatasi *outlier*.
*   Membatasi nilai di kolom `Profit` dengan batas bawah -674.123 untuk mengatasi *outlier*.
## Data Analysis
Analisis dilakukan untuk menentukan kriteria transaksi yang memberikan keuntungan yang besar, khususnya yang lebih dari rata-rata yaitu 25.54.
### Berdasarkan Waktu
Analisis yang dilakukan pada bagian ini adalah sebagai berikut:
*   Melihat pertumbuhan rata-rata dan total keuntungan setiap tahunnya.
*   Melihat pertumbuhan rata-rata dan total keuntungan setiap bulannya untuk masing-masing tahun.
  Dari kedua analisis tersebut ditemukan bahwa total keuntungan pertahun konsisten naik, tapi rata-rata keuntungan pertahun menurun di 2 tahun terakhir. Selain itu, tidak terlihat tren rata-rata keuntungan perbulan, tapi jumlah transaksi dan total keuntungan cenderung lebih tinggi pada akhir tahun dibanding pada awal tahun.
### Berdasarkan Lokasi
Analisis yang dilakukan pada bagian ini adalah sebagai berikut:
*   Menentukan region dengan rata-rata dan total keuntungan tertinggi
*   Membuat *dataframe* yang berisi jumlah penjualan, rata-rata keuntungan, dan total keuntungan berdasarkan subregion.
*   Menentukan subregion dengan total keuntungan tertinggi yang rata-rata keuntungannya lebih dari 25.54.
*   Membuat *dataframe* yang berisi jumlah penjualan, rata-rata keuntungan, dan total keuntungan berdasarkan negara.
*   Menentukan negara dengan total keuntungan tertinggi yang rata-rata keuntungannya lebih dari 25.54.
*   Membuat *dataframe* yang berisi jumlah penjualan, rata-rata keuntungan, dan total keuntungan berdasarkan kota.
*   Menentukan kota di negara yang total keuntungannya tinggi dengan total keuntungan tertinggi yang rata-rata keuntungannya lebih dari 25.54.
  Dari analisis ini didapatkan bahwa region AMER dan EMEA memiliki keuntungan yang tinggi, subregion dengan keuntungan tertinggi adalah NAMER dan UKIR, negara dengan keuntungan tertinggi adalah amerika serikat, inggris, kanada, brazil, dan spanyol, lebih tepatnya di kota London, New York, Toronto, Los Angeles, Sao Paulo, dan Seattle. 
### Berdasarkan Pembeli
Analisis yang dilakukan pada bagian ini adalah sebagai berikut:
*   Membuat *dataframe* yang berisi jumlah penjualan, rata-rata keuntungan, dan total keuntungan berdasarkan perusahaan pembeli.
*   Menentukan perusahaan yang memberi keuntungan tertinggi dengan rata-rata keuntungannya lebih dari 25.54.
*   Menentukan industri dengan persentase perusahaan yang memenuhi kriteria sebelumnya yang tinggi.
*   Membuat *dataframe* yang berisi jumlah penjualan, rata-rata keuntungan, dan total keuntungan berdasarkan perusahaan industri.
*   Menentukan industri yang memberi keuntungan tertinggi dengan rata-rata keuntungannya lebih dari 25.54.
  Dari analisis ini didapatkan bahwa perusahaan yang memberikan keuntungan tertinggi adalah Kroger, Bank of America Corp., Valero Energy, Ford Motor, dan Siemens, serta industri yang memberikan keuntungan tertinggi adalah manufacturing, retail, dan healthcare.
### Berdasarkan Penjualan
Analisis yang dilakukan pada bagian ini adalah sebagai berikut:
*   Membuat *dataframe* yang berisi jumlah penjualan, rata-rata keuntungan, dan total keuntungan berdasarkan perusahaan produk.
*   Menentukan produk dengan total keuntungan tertinggi yang rata-rata keuntungannya lebih dari 25.54.
*   Menentukan apakah ada perbedaan jumlah produk antara transaksi yang keuntungannya lebih dari 25.54 dan yang tidak.
*   Menentukan pengaruh diskon terhadap keuntungan.
  Dari analisis ini didapat bahwa produk yang memberikan keuntungan tertinggi adalah Site Analytics, Data Smasher, dan FinanceHub. Transaksi yang menjual banyak produk sekaligus dan transaksi dengan diskon di bawah 40% cenderung memberikan keuntungan yang lebih besar. 
## Kesimpulan
Berdasarkan analisis yang telah dilakukan, kita bisa menyimpulkan kriteria dari transaksi yang memberikan keuntungan yang tinggi:
*   Berasal dari subregion NAMER, UKIR, atau APAC.
*   Berasal dari negara amerika serikat, inggris, kanada, brazil, dan spanyol. Lebih spesifiknya kota London, New York, Toronto, Los Angeles, Sao Paulo, dan Seattle.
*   Berasal dari industri manufacturing, energy, dan healthcare, khususnya perusahaan Valero Energy, Ford Motor, dan Siemens, serta perusahaan Kroger dan Bank of America Corp. yang termasuk di industri lain.
*   Menjual produk Site Analytics, Data Smasher, dan FinanceHub.
*   Menjual lebih banyak produk sekaligus.
*   Diskon kurang dari 40%.
