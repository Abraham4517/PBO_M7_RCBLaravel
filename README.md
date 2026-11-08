# Routing, Controller & Blade

1. **Route (`/kategori/{nama}`):** 
   Menerima request URL dengan parameter dinamis (contoh: `pemrograman`). Route akan memanggil method `show()` pada `KategoriController` dan mengirimkan parameter `{nama}` tersebut.
2. **Controller (`KategoriController@show`):** 
   Bertugas sebagai penyedia data bisnis. Controller menyimpan data *array multidimensi* yang berisi daftar buku yang dikelompokkan berdasar kategori. Controller mem-filter array menggunakan parameter dari Route, lalu melemparkan variabel `$namaKategori` dan `$daftarBuku` menuju View.
3. **Blade View (`kategori.show`):**
   Menerima data dari Controller dan melakukan *rendering* antarmuka. 
   - Directive `@if`, `@elseif`, dan `@else` digunakan untuk memvalidasi apakah array bernilai null (kategori fiktif), bernilai 0 (kategori kosong), atau memiliki isi.
   - Directive `@foreach` digunakan di dalam blok `@else` untuk mencetak setiap buku menjadi elemen *list* HTML.
