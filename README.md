TUGAS 7
1. Jelaskan apa itu widget tree pada Flutter dan bagaimana hubungan parent-child (induk-anak) bekerja antar widget.
   Widget tree pada Flutter adalah struktur hierarki yang terdiri atas widget-widget, widget-widget ini disusun untuk menentukan tata letak dan UI pada aplikasi. Setiap widget dalam tree ini dapat memiliki nol atau lebih child widget, 
   proses ini membentuk hubungan parent-child yang menentukan bagaimana UI disusun. Parent bertanggung jawab atas penempatan, pengaturan, dan konfigurasi children, sementara child mewakili elemen UI spesifik.
2. Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya.
   a. MaterialApp: Fungsinya adalah untuk menjadi root dalam aplikasi, mengatur tema, mengonfigurasi material desain, dan menyediakan scaffold.
   b. Scaffold: Fungsinya adalah untuk menjadi wadah utama yang menata letak elemen-elemen UI di sebuah halaman, mengatur AppBar, menampilkan Body, mengatur navigasi, menambahkan FloatingActionButton, dan mendukung SnackBar.
   c. AppBar: Fungsinya adalah untuk menampilkan header aplikasi, dalam tugas ini yaitu menampilkan header tulisan "Sofita Shop".
   d. Text: Fungsinya adalah untuk menampilkan teks, pada tugas ini contohnya yaitu nama, NPM, dan lain sebagainya.
   e. Column: Fungsinya adalah untuk menyusun widget secara vertikal.
   f. Row: Fungsinya adalah untuk menyusun widget secara horizontal.
   g. Padding: Fungsinya adalah untuk memberi jarak di sekitar widgetnya.
   h. SizedBox: Fungsinya adalah untuk memberikan space antar elemen.
   i. Center: Fungsinya untuk menempatkan widget di tengah.
   j. GridView.count: Fungsinya adalah untuk menampilkan daftar ItemCard dalam bentuk grid.
   k. Card: Fungsinya adalah membuat tampilkan yang bentuknya seperti kartu (kotak kartu).
   l. Container: Fungsinya untuk membungkus widget lain, mengatur ukuran, dan menata tampilan visual.
   m. Icon: Fungsinya untuk menampilkan icon, misalnya dalam tugas ini yaitu menampilkan icon shopping_cart_rounded, my_library_books, dan add.
   n. Material: Fungsinya untuk memberikan efek material desain pada ItemCard.
   o. InkWell: Fungsinya untuk membuat widgetnya interaktif (bisa ditekan), menangani gestur, dan membuat efek visual.
   p. SnackBar: Fungsinya untuk menampilkan notifikasi di bawah layar ketika bagian itemCard ditekan.
   q. MediaQuery: Fungsinya untuk mengambil informasi tentang ukuran layar, orientasi, dan properti lainnya supaya UI bisa responsif terhadap berbagai ukuran perangkat.
3. Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini sering digunakan sebagai widget root.
   MaterialApp adalah widget yang digunakan sebagai root dari seluruh antarmuka aplikasi flutter, fungsinya adalah untuk menyediakan tema material design untuk seluruh aplikasi, menyediakan navigasi dan routing antar halaman, mengatur 
   judul aplikasi, tema, dan debug banner. MateralApp sering digunakan sebagai root karena seluruh widget di bawahnya membutuhkan context material design, tanpa adanya MaterialApp, widget seperti Scaffold, AppBar, dan SnackBar tidak 
   dapat diimplementasikan dengan benar.
4. Jelaskan perbedaan antara StatelessWidget dan StatefulWidget. Kapan kamu memilih salah satunya?
   a. StatelessWidget: StatelessWidget merupakan widget yang bersifat immutable jika user melakukan suatu tindakan pada aplikasi, biasanya StatelessWidget ini digunakan untuk menampilkan konten statis atau elemen UI yang tidak perlu diubah 
      sebagai respons terhadap interaksi pengguna.
   b. StatefulWidget: StatefulWidget adalah widget yang bersifat dinamis dan dapat berubah ketika pengguna melakukan interaksi tertentu atau dapat berubah seiring berjalannya waktu, StatefulWidget ini digunakan untuk elemen UI interaktif 
      yang perlu memperbarui konten atau tampilannya berdasarkan interaksi dari pengguna.
5. Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di metode build?
   BuildContext adalah abstract class dalam kerangka kerja Flutter yang merepresentasikan handle untul lokasi widget di widget tree, setiap widget memiliki BuildContext-nya sendiri yang menjafi induk dati BuildContext untuk widget turunannya. 
   Dalam aplikasi Flutter, BuildContext digunakan untuk menemukan widget terdekat dari jenis tertentu, misalnya jika kita memiliki widget Scaffold fi widget tree dan ingin menampilkannya ke SnackBar, maka kita akan menggunakan BuildContext 
   untuk bisa menemukan widget Scaffold terdekat. BuildContext juga digunakan dalam widget tree, BuildContext adalah referensi ke elemen dalam widget tree. Dalam method build, BuildContext digunakan seperti: Theme.of(context).colorScheme.primary 
   artinya, context digunakan untuk mengambil tema warna dari parent widget (MaterialApp).
6. Jelaskan konsep "hot reload" di Flutter dan bagaimana bedanya dengan "hot restart".
   Hot reload adalah fitur pengembangan aplikasi yang memungkinkan pengembang untuk memperbarui kode dan melihat hasilnya secara instan tanpa memulai ulang aplikasi sehingga proses pengembangan, debugging, dan iterasi UI dapat berjalan dengan 
   lebih cepat. Hot reload ini bekerja dengan cara menyuntikkan kode yang telah diubah ke dalam aplikasi yang sedang running tanpa mengubah atau mengganti seluruh aplikasinya, misalnya ketika pengembang mengubah label text, perubahannya akan 
   terlihat tanpa kehilangan data yang sebelumnya sudah ada dalam aplikasi. Bedanya hot reload dari hot restart yaitu kecepatannya, hot reload bisa sangat cepat karena tidak melakukan rebuild total, hanya melakukan rebuild pada beberapa bagian 
   saja, selain itu hot reload juga mempertahankan state sementara hot restart mereset state ke kondisi awal, namun hot reload hanya dapat digunakan hanya saat mengubah UI atau logika yang ukurannya kecil, misalnya mengganti teks, namun kika 
   ingin menambah variabel baru di main() atau mengubah struktur dari StatefulWidget, kita perlu menggunakan hot restart.