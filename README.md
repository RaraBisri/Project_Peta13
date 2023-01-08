# Langkah kerja

1. Di QGIS, mari muat file gambar. Pergi ke Layer ‣ Add Layer ‣ Add Raster Layer .

2. Dalam dialog Pengelola Sumber Data pilih Raster. Di bawah Sumber klik ...dan cari yang diunduh BX24_GeoTifv1-02.tifdan klik Buka . Kemudian klik Tambah diikuti dengan Tutup.

3. Ini adalah file raster yang besar, dan Anda mungkin memperhatikan bahwa saat Anda memperbesar atau menggeser peta, peta memerlukan sedikit waktu untuk merender gambar. QGIS menawarkan solusi sederhana untuk membuat raster memuat lebih cepat dengan menggunakan Image Pyramids . QGIS membuat petak pra-render pada resolusi yang berbeda, dan ini disajikan kepada Anda alih-alih raster penuh. Ini membuat navigasi peta cepat dan responsif. Klik kanan BX24_GeoTifv1-02layer dan pilih Properties .

4. Dalam dialog Properti Lapisan , Pilih tab Piramida . Tahan Ctrltombol dan pilih semua resolusi yang ditawarkan di panel Resolusi . Biarkan opsi lain ke default dan klik Bangun piramida .

5. Setelah proses selesai, kotak dialog akan menampilkan piramida tanpa tanda silang. Ini menandakan pembangunan Piramida Gambar sudah selesai. Klik Oke .

6. Sebelum kita mulai, kita perlu mengatur Opsi Digitalisasi default . Buka Pengaturan ‣ Opsi… .

7. Pilih tab Digitalisasi di dialog Opsi . Centang Enable snapping by default di bawah bagian Snapping . Dalam mode snap Default pilih Vertex . Ini akan memungkinkan Anda untuk menjepret ke simpul terdekat. Saya juga lebih suka menyetel toleransi gertakan default dan Radius pencarian untuk suntingan titik dalam piksel daripada unit peta. Ini akan memastikan bahwa jarak jepretan tetap konstan terlepas dari tingkat zoom. Tergantung pada resolusi layar komputer Anda, Anda dapat memilih nilai yang sesuai. Klik Oke .

8. Sekarang kita siap untuk memulai digitalisasi. Pertama-tama kita akan membuat layer jalan dan mendigitalkan jalan di sekitar area taman. Klik Layer ‣ Create Layer ‣ New GeoPackage Layer… ikon dari Panel. GeoPackage adalah format data terbuka, non-proprietary, platform-independen, dan berbasis standar untuk sistem informasi geografis yang diimplementasikan sebagai wadah database SQLite. Ini membuatnya lebih mudah untuk memindahkannya daripada sekumpulan shapefile. Dalam tutorial ini, kami membuat beberapa lapisan poligon dan lapisan garis sehingga GeoPackage akan lebih cocok. Anda selalu dapat memuat GeoPackage dan mengekspor layer sebagai shapefile atau format lain yang Anda inginkan.

9.  Dalam dialog Lapisan GeoPackage Baru , klik tombol … dan simpan database GeoPackage baru bernama digitizing.gpkg. Pilih nama Tabel sebagai Roadsdan pilih LineStringsebagai jenis Geometri . Peta topografi dasar adalah CRS.EPSG:2193 - NZGD 2000

10. Saat membuat lapisan GIS, Anda harus memutuskan atribut setiap fitur. Karena ini adalah layer jalan, kita juga akan memiliki dua atribut utama - Nama dan Kelas. Di Bidang Baru Masukkan Namejenis data Teks, dengan panjang Maksimum50 dan klik Tambahkan ke daftar atribut. Sekarang buat atribut baru dengan tipe Text data , dengan sebagai Maximum length . Klik OkeClass50

11. Setelah Roadslayer dimuat, klik tombol Toggle Editing untuk menempatkan layer dalam mode edit.

12. Klik tombol Tambahkan Fitur Garis . Klik pada kanvas peta untuk menambahkan simpul baru. Tambahkan simpul baru bersama dengan fitur jalan. Setelah Anda mendigitalkan ruas jalan, klik kanan untuk mengakhiri fitur.

13. Setelah Anda mengklik kanan untuk mengakhiri fitur, Anda akan mendapatkan dialog pop-up yang disebut Road - Feature Attributes . Di sini Anda dapat memasukkan atribut dari fitur yang baru dibuat. Lewati memasukkan nilai apa pun untuk fid karena ini adalah id berurutan yang akan dibuat secara otomatis. Masukkan nama jalan seperti yang tertera di peta topo. Secara opsional, tetapkan juga nilai Kelas Jalan. Klik Oke .

14. Gaya default dari layer garis baru adalah garis tipis. Mari kita ubah untuk lebih melihat fitur digital di kanvas. Pilih Roadslayer dan klik Layer Styling Panel .

15. Di Layer Styling Panel , cari gaya layer jalan yang berbeda. Pilih . Klik Oke .topo road.

16. Sekarang lapisan jalan akan terlihat jelas. Jika Anda puas dengan pekerjaannya, klik tombol Save Layer Edits untuk menyimpan perubahan.

17. Sebelum kita mendigitalkan jalan yang tersisa, penting untuk memperbarui beberapa pengaturan snap penting lainnya untuk membuat lapisan bebas kesalahan. Klik kanan pada ruang mana pun di area bilah alat dan aktifkan bilah alat Snapping.

18. Sekarang Enable Snapping (Magnet Icon) akan muncul di panel. Klik untuk mengaktifkannya dan pilih All Layers dan pilih .Open Snapping Options..

19. Dalam dialog Snapping options , klik Snapping on Intersection , yang memungkinkan Anda menjepret perpotongan lapisan latar belakang.

20. Sekarang Anda dapat mengklik tombol Tambahkan fitur dan mendigitalkan jalan lain di sekitar taman. Pastikan untuk mengklik Simpan Hasil Editan setelah menambahkan fitur baru untuk menyimpan pekerjaan Anda. Alat yang berguna untuk membantu Anda mendigitalkan adalah Alat Vertex . Klik tombol Alat Vertex dan pilih .Vertex Tool (Current Layer).

21. Setelah alat simpul diaktifkan, klik fitur apa saja untuk menampilkan simpul. Klik pada sembarang titik untuk memilihnya. Titik akan berubah warna setelah dipilih. Sekarang Anda dapat mengklik dan menyeret mouse Anda untuk memindahkan vertex. Ini berguna ketika Anda ingin melakukan penyesuaian setelah fitur dibuat. Anda juga dapat menghapus simpul yang dipilih dengan mengklik Deletetombol. ( di mac)Option+Delete.

22. Setelah Anda selesai mendigitalkan semua jalan, klik tombol Toggle Editing . Klik Simpan .

23. Sekarang kita akan membuat layer lain untuk mendigitalkan taman sebagai poligon. Klik Layer Create Layer New GeoPackage Layer… icon dari Panels. Pada dialog New GeoPackage Layer , klik tombol … dan pilih database GeoPackage bernama digitizing.gpkg. Beri nama layer baru sebagai atribut yang disebut Parks. Pilih MultiPolygonsebagai Jenis . Peta topografi dasar adalah CRS. Klik Oke . Di Bidang Baru Masukkan , dan ketik sebagai Data teks , dengan Panjang maksimum dan klik :guilabel: Tambahkan ke Daftar Bidang.. Klik Oke .EPSG:2193 - NZGD 2000Name50.

24. Dialog pop-up akan muncul. Pilih tombol Tambahkan Lapisan Baru .

25. Sekarang pilih layer Parkslalu klikroad Toggle Editing dan klik tombol Add feature dan klik pada kanvas peta untuk menambahkan simpul poligon. Digitalkan poligon yang mewakili taman. Pastikan Anda menjepret simpul jalan sehingga tidak ada celah antara poligon taman dan garis jalan. Klik kanan untuk menyelesaikan poligon.

26. Masukkan nama taman di jendela pop-up Taman - Atribut Fitur .

27. Sekarang mendigitalkan wilayah atas taman. Masukkan nama taman dan simpan perubahannya.

28. Sekarang, sebelum mendigitalkan poligon dalam, mari atur pengaturan yang dapat memudahkan pekerjaan ini. Lapisan Multi-Poligon menawarkan pengaturan berguna lainnya yang disebut Hindari persim
 
