# StrukturData-Q1-2501010221-Japa-A

1. Karakteristik Memori dan Akses Data
   
  Operasi akses elemen pada Array bisa dilakukan dengan waktu konstan O(1) karena data pada array disimpan di alamat memori yang berurutan (kontinu). Setiap elemen memiliki indeks seperti 0, 1, 2, dan seterusnya. Karena alamat memori tersusun berurutan, komputer dapat langsung menghitung lokasi elemen yang ingin diakses berdasarkan indeksnya. Jadi tidak perlu mencari data satu per satu.
Berbeda dengan Singly Linked List, data disimpan di memori yang tidak berurutan (non-kontinu). Setiap data berada dalam sebuah node yang terhubung dengan pointer ke node berikutnya. Jika ingin mengakses elemen tertentu, kita harus mulai dari node pertama (head) lalu mengikuti pointer sampai menemukan elemen yang dicari.
Karena harus melewati node satu per satu, waktu yang dibutuhkan menjadi linear atau O(n).

Jadi kesimpulannya, Array lebih cepat dalam akses data karena memori yang berurutan, sedangkan Linked List membutuhkan penelusuran node karena memori tidak berurutan.

2. Analisis Efisiensi Operasi Manipulasi
   
  Linked List lebih diunggulkan dibandingkan Array pada operasi penyisipan (insertion) dan penghapusan (deletion) terutama ketika dilakukan di tengah data atau ketika ukuran data sering berubah.
Pada Array, jika kita ingin menambah atau menghapus elemen di tengah, maka elemen-elemen setelah posisi tersebut harus digeser agar tidak ada ruang kosong atau tumpang tindih. Proses menggeser banyak elemen ini membutuhkan waktu yang cukup lama, sehingga kompleksitas waktunya menjadi O(n).
Sedangkan pada Linked List, proses penyisipan atau penghapusan cukup dengan mengubah pointer pada node yang terhubung. Kita tidak perlu memindahkan data lain seperti pada array. Jika posisi node sudah diketahui, maka prosesnya bisa dilakukan dengan lebih cepat yaitu sekitar O(1).

  Secraa teoritis, Linked List lebih efisien karena:
- Tidak perlu menggeser elemen lain saat insert atau delete.
- Ukuran struktur data bisa berubah secara dinamis.
- Operasi manipulasi hanya melibatkan perubahan pointer antar node.
  
Karena itu, Linked List lebih cocok digunakan pada kondisi di mana data sering ditambah atau dihapus, terutama di bagian tengah struktur data.

3. Konsep Doubly Linked List

  Pada Doubly Linked List, setiap node memiliki tiga bagian utama yaitu prev, data, dan next. Bagian data digunakan untuk menyimpan nilai atau informasi yang ada di dalam node tersebut. Kemudian prev adalah pointer yang menunjuk ke node sebelumnya, sedangkan next adalah pointer yang menunjuk ke node berikutnya. Dengan adanya dua pointer ini, setiap node mengetahui posisi node sebelum dan sesudahnya di dalam linked list.
Berbeda dengan Singly Linked List yang hanya memiliki satu pointer yaitu next, Doubly Linked List memiliki pointer tambahan yaitu prev. Keberadaan pointer tambahan ini membuat penggunaan memori menjadi lebih besar karena setiap node harus menyimpan dua alamat pointer sekaligus. Jadi secara penggunaan memori, Doubly Linked List lebih boros dibandingkan Singly Linked List. 

  Namun, pointer tambahan tersebut memberikan kelebihan dalam hal fleksibilitas penelusuran data. Pada Doubly Linked List kita bisa melakukan traversal atau penelusuran ke dua arah, yaitu dari depan ke belakang menggunakan pointer next, dan dari belakang ke depan menggunakan pointer prev. Hal ini membuat beberapa operasi menjadi lebih mudah dilakukan, misalnya ketika ingin kembali ke node sebelumnya tanpa harus memulai lagi dari node pertama. Jadi meskipun membutuhkan memori lebih banyak, Doubly Linked List lebih fleksibel dalam proses navigasi dan manipulasi data dibandingkan Singly Linked List.

4. Mekanisme Circular Linked List

  Circular Linked List adalah jenis linked list di mana node terakhir tidak menunjuk ke NULL, tetapi menunjuk kembali ke node pertama (head) sehingga membentuk sebuah lingkaran. Hal ini yang membedakan Circular Linked List dengan Linked List biasa. Pada Linked List biasa, node terakhir selalu menunjuk ke NULL yang menandakan bahwa daftar telah berakhir. Sedangkan pada Circular Linked List, karena node terakhir menunjuk kembali ke node pertama, maka proses penelusuran dapat terus berulang tanpa ada akhir yang jelas sampai program menghentikannya.
  
  Secara teoritis, struktur melingkar ini membuat semua node saling terhubung dalam satu siklus sehingga tidak ada node yang benar-benar menjadi akhir dari list. Hal ini membuat perpindahan dari node terakhir ke node pertama menjadi lebih mudah karena tidak perlu kembali secara manual ke awal list.
  
  Salah satu contoh penggunaan Circular Linked List adalah pada algoritma Round Robin Scheduling dalam sistem operasi. Pada sistem ini, beberapa proses akan mendapatkan giliran menggunakan CPU secara bergantian. Setelah proses terakhir selesai menjalankan bagiannya, sistem akan kembali lagi ke proses pertama dan siklus tersebut terus berulang. Struktur Circular Linked List cocok digunakan pada kondisi seperti ini karena alur datanya bersifat berulang atau siklus.

5. Array Dinamis di Python

  Pada Python, list sebenarnya diimplementasikan sebagai Dynamic Array, yaitu array yang ukurannya bisa bertambah secara otomatis ketika dibutuhkan. Saat kita melakukan operasi append(), Python akan menambahkan elemen baru di bagian akhir list. Namun, jika kapasitas array yang tersedia sudah penuh, maka Python akan melakukan beberapa proses di balik layar.

  Pertama, Python akan membuat array baru dengan kapasitas yang lebih besar dari array sebelumnya. Biasanya ukuran kapasitas baru dibuat lebih besar agar tidak perlu sering-sering melakukan perubahan ukuran ketika elemen terus ditambahkan. Setelah itu, semua elemen dari array lama akan disalin ke array yang baru. Proses penyalinan ini dilakukan satu per satu hingga semua data berpindah ke tempat yang baru. Setelah proses penyalinan selesai, elemen baru yang ditambahkan melalui append() akan dimasukkan ke posisi terakhir pada array yang baru tersebut.

  Karena proses penyalinan data membutuhkan waktu yang lebih lama, operasi ini secara teoritis bisa memakan waktu O(n) ketika proses perubahan kapasitas terjadi. Namun karena proses tersebut tidak terjadi setiap kali append(), maka secara rata-rata operasi append() pada Python list tetap dianggap memiliki kompleksitas waktu O(1). Hal ini membuat Python list tetap efisien digunakan walaupun ukurannya dapat berubah secara dinamis.
