# StrukturData-Q1-2501010016-IGUSTINGURAHDWIANDIKAPUTRA-KLS-A
# 1. Karakteristik Memori dan Akses Data
Jelaskan mengapa operasi akses elemen pada Array dapat dilakukan dalam waktu konstan
O(1), sedangkan pada Singly Linked List membutuhkan waktu linear O(n). Hubungkan
jawaban Anda dengan konsep alamat memori (kontinu vs non-kontinu).


# JAWABAN : 
Array disimpan dalam blok memori yang kontinu. Artinya, elemen-elemennya diletakkan berdampingan tanpa celah. Karena sifatnya yang berurutan dan setiap elemen memiliki ukuran yang sama, komputer tidak perlu mencari elemen satu per satu.

Sebaliknya, Singly Linked List menggunakan memori non-kontinu. Karena setiap elemen (node) tersebar di lokasi memori yang acak.


# 2. Analisis Efisiensi Operasi Manipulasi
Dalam kondisi apa sebuah Linked List lebih diunggulkan dibandingkan Array untuk operasi penyisipan (insertion) dan penghapusan (deletion) data? Berikan alasan teoritisnya.


# JAWABAN :
Linked List lebih unggul dibandingkan Array dalam kondisi sering terjadi penyisipan (insertion) atau penghapusan (deletion) di tengah atau awal struktur data, terutama jika jumlah elemennya sangat besar.

Array: Saat menyisipkan elemen di tengah, semua elemen setelahnya harus digeser (shifting) satu posisi ke kanan untuk memberi ruang. Hal ini memakan waktu O(n).

Linked List: Tidak ada pergeseran data. Anda hanya perlu mengubah arah pointer pada node tetangga untuk menyambungkan atau memutus hubungan. Operasi ini secara teknis adalah $O(1)$ jika posisi node yang akan dimanipulasi sudah ditemukan.

# 3. Konsep Doubly Linked List
Jelaskan struktur anatomi dari sebuah node pada Doubly Linked List. Apa dampak keberadaan pointer tambahan tersebut terhadap penggunaan memori serta fleksibilitas penelusuran dibandingkan dengan Singly Linked List?

# JAWABAN : 
Sebuah node pada Doubly Linked List memiliki tiga komponen utama:

Data: Nilai yang disimpan.

Pointer Next: Alamat memori node berikutnya.

Pointer Prev: Alamat memori node sebelumnya.

Memori: Penggunaan memori lebih boros dibandingkan Single Linked List, karena setiap node harus menyimpan satu pointer tambahan (prev).

Fleksibilitas: Jauh lebih fleksibel karena memungkinkan navigasi dua arah (maju dan mundur). Hal ini mempermudah operasi seperti menghapus node tertentu jika kita sudah memegang referensi node tersebut, tanpa harus mencari node sebelumnya dari awal.

# 4. Mekanisme Circular Linked List
Apa yang membedakan Circular Linked List dari Linked List biasa secara teoritis? Sebutkan satu contoh skenario penggunaan (use case) di mana struktur melingkar ini lebihefektif digunakan.


# JAWABAN :
Secara teoritis, perbedaan utama terletak pada node terakhir (tail). Pada Linked List biasa, pointer next pada tail bernilai null. Pada Circular Linked List, pointer next pada tail kembali menunjuk ke head, sehingga membentuk lingkaran tanpa ujung.

Penjadwalan Round Robin (Sistem Operasi): Digunakan untuk menggilir jatah waktu CPU antar aplikasi secara adil. Setelah aplikasi terakhir selesai diproses sebentar, sistem langsung kembali ke aplikasi pertama secara otomatis melalui struktur melingkar ini.


# 5. Array Dinamis di Python
Python list secara internal diimplementasikan sebagai Dynamic Array. Jelaskan mekanisme yang terjadi ”di balik layar” ketika sebuah Dynamic Array kehabisan kapasitas saat
melakukan operasi append.


# JAWABAN : 
Ketika sebuah list di Python kehabisan kapasitas saat melakukan append, terjadi mekanisme yang disebut Dynamic Resizing (Over-allocation):

Alokasi Baru: Python akan memesan blok memori baru yang lebih besar.

Penyalinan (Copying): Semua elemen dari array lama disalin ke array baru yang lebih luas.

Penghapusan: Memori array yang lama dibebaskan (dihapus).

Append: Elemen baru ditambahkan ke ruang kosong di array baru.
